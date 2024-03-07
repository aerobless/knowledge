# ☕ VoxxedDays Zurich 2024

## Cool Java Stuff

* [CodeScene](https://codescene.com/): Code Analysis / Code Health report, not free
* HTTPClient
* Structured Concurrency
* String Templates
* [Simple FileServer (JDK 20+)](https://download.java.net/java/early\_access/loom/docs/api/jdk.httpserver/com/sun/net/httpserver/SimpleFileServer.html)

## Cool sites

* [https://inside.java/](https://inside.java/)
* [https://dev.java/](https://dev.java/)

## Cool IntelliJ Stuff

* Distraction free mode for focused work -> shortcut
* set custom project icon -> icon.png in idea folder
* Live template `cmd+j`
  * probably not really needed that much anymore due to AI
* **Debugging**
  * Expression Breakpoints in line for streams/lambdas
    * In Debugger: **Trace Current Stream Chain** -> visualises how the chain looks like
  * Interface Breakpoints
  * shift-click on variable, then side gutter -> have advanced tooling for breakpoint, can evaluate e.g. x = null everytime when the code runs by the breakpoint
  * Analyze dataflow: can see how many branches reach the same code
  * Have breakpoint only active if previous non suspending breakpoint was reached, can help to only get to specific state of method

## Cool AI Stuff

### ChatGPT

#### Priming tips

* Tell it: start every response with >, to produce markdown, then you see when it runs out of context
* Improve personal base prompt to reduce length a bit
* Base prompt
  * no ai disclosure
  * tell it how it should respond: asciidoc, prefered libraries etc.
* prime the context with small-talk

#### Solving problems

* When uploading documents, tell it to summarise before starting work
* Images in pdfs etc. are ignored, upload them separatly and ask it to understand
* **Tell it to ask questions about the task**
* Ask it to repeat the task you want to solve
* Rephrase the prompt instead of making a new prompt to keep the context shorter and to prevent poisoning the session with bad information.
* Let the system first describe with text the context and then ask it e.g. for a plant uml diagram
  * Ask the model to first explain how it would solve the problem

### Java ML

* Classical programming vs. machine learning
  * Classical programming -> we define the rules and the machine follows them to get an output
  * Machine learning -> we let the machine figure out the rules to automate the task
* Java Libs for ML
  * [DL4J](https://deeplearning4j.konduit.ai/), [DJL](https://djl.ai/), [Tribuo (Oracle)](https://tribuo.org/), JSR381 (Image Recognition Spec)
* recommendation: [DJL](https://djl.ai/), it's an interface to the real engines (pytorch etc.)
  * has pretrained model for tagging images, etc. z.B: resNet
  * easy to integrate

## Companies present at VoxxedDays

Redhat, ZKB, BJB, 47North, claranet, ELCA, 42Talents, Axa
