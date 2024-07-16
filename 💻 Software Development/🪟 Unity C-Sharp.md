# Async tasks - [Best Practices](https://youtu.be/7eKi6NKri6I?t=1769)

## Await within task to propagate exceptions

```csharp
public static async Task<bool> taskName()
{    
    Task pressBackButtonTask = Utils.WaitForPRessBackButton();
    Task finishedTask = await Task.WhenAny(pressBackButtonTask, ..);
    
    await finishedTask; // Propagate exception if the task finished because of exception
    
    return finishedTask == pressBackButtonTask.Result;
}
```

## Manual Cancellation

Every async function should take a cancellation token. This is needed to cancel a function for example when a gameobject is destroyed.

```csharp
public static async Task<bool> taskName(CancellationToken ct)
{    
    Task pressBackButtonTask = Utils.WaitForPRessBackButton(ct); // here
    Task finishedTask = await Task.WhenAny(pressBackButtonTask, ..);
    
    await finishedTask; // Propagate exception if the task finished because of exception
    
    return finishedTask == pressBackButtonTask.Result;
}
```

## Clean up remaining tasks

```csharp
public static async Task<bool> taskName(CancellationToken ct)
{    

    var linkedCts = CancellationTokenSource.CreateLinkedTokenSource(ct);
    var linkedCt = linkedCts.Token;
    
    Task pressBackButtonTask = Utils.WaitForPRessBackButton(linkedCt); // NEW linkedCt
    Task finishedTask = await Task.WhenAny(pressBackButtonTask, ..);
    
    await finishedTask; // Propagate exception if the task finished because of exception
    linkedCts.Cancel(); //NEW
    
    return finishedTask == pressBackButtonTask.Result;
}
```

### Dispose linked CancellationTokenSource

Dispose of the token source via "using block". Otherwise there could be a memory leak when the task is cancelled externally.

```csharp
using (var linkedCts = CancellationTokenSource.CreateLinkedTokenSource(ct)){
    var linkedCt = linkedCts.Token;
    // do the work
    await finishedTask;
    linkedCts.Cancel()
    return finishedTask == pressBackButtonTask.Result;
}
```

alternatively a try-finally block can be used:

```csharp
var linkedCts = CancellationTokenSource.CreateLinkedTokenSource(ct);
try {
    var linkedCt = linkedCts.Token;
    // do the work
    await finishedTask;
    linkedCts.Cancel()
    
    return finishedTask == pressBackButtonTask.Result;
}
finally
{
    linkedCts.Cancel()
    // do some other ending work, e.g. play closing animation of popup
}
```

### [When to choose Async vs. Coroutines](https://youtu.be/7eKi6NKri6I?t=2380)

1. Use async when you deal with IO (User Input, Network Calls)
2. Use coroutines for fire-and-forget routines.
3. Don't intertwine them