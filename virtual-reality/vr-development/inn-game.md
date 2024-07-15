# Inn Game

The Inn Game is currently looked in my [PeiramaVR](https://github.com/aerobless/PeiramaVR) repository. Peirama mean experiment in greek.

## Inspiration

The game is inspired by the fantasy story web series "[The Wandering Inn](https://wanderinginn.com)". The basic idea is that you're running an inn where you have to make food and deal with customers.

## Gameplay Loop(s)

The core gameplay loop "Run the inn" is structured into several sub loops that the player can participate in at will. The player finds the inn in a non functional state, dusty, broken tools, skeleton etc. The player can then repair the inn and open it for customers. Customers will leave the inn dirty again so the player will have to do some maintenance. Additional goblins may attack occasionally requiring the player to defend the inn. Other "events" are possible too.

The main focus is that any "work" is physical and fun. E.g. cleaning requires sweeping a virtual broom. Serving customers mean creating a dish (potentially different outcomes on what food you serve) and bringing it over to a customer sitting at a table.

There is also a discovery component involved. The game should not prompt you to take certain actions by showing you a tutorial/wall of text. Instead the players sees e.g. the dirt and a nearby broom glowing slightly. And if the player does not clean up the dirt customers may complain about it. So the player learns to deal with the dirt.

* Run the inn (Core Gameplay Loop)
  * Clean the inn
    * Use broom to clean up piles of dirt
    * remove bodies (e.g. dead goblins) from the inn by dragging them outside
  * Serve customers
    * Switch open/closed sign outside of inn to attract customers
      * customers come in and demand food or drinks
      * prepare food in kitchen
        * combine various ingredients -> bad combinations may result in unhappy customers
      * bring food to customer & collect pay
  * Defend inn
    * various threats may put the inn in danger, e.g. goblin raid, spider attack
      * kill attackers
  * Gather ingredients
    * some ingredients may run out, e.g. firewood, water, mushrooms etc.
      * gather firewood by cutting down trees
        * make fire in oven
      * gather water from well
      * gather mushrooms or other food items

## Tasks

*   Inn Customer Loop
  *   Player can control customers by switching sign from closed to open
  *   Customer walks from city to inn
  *   Customer AI avoids player with pathfinding obstacle
  * [x] Customer enters inn
  * [x] Customer sits down
  * [x] Customer takes beer
    *   customer checks if beer mug is full before taking it
  * [x] Customer drinks beer
    *   beer is emptied for each drink
  *   Customer drops empty mug on table
  *   Customer drops money on table
    *   Model for coins
    *   Depending on happiness customer gives more or less coins
  *   Customer gets up and leaves inn
  *   Player gathers coins and puts them in safe / cashiers register
  *   Used dishes are considered dirty
    *   Player can wash used dishes
*   Cleaning Inn Loop
  *   Dropping food creates dirt
  * [x] Dirt can be cleaned up
  * [x] Cleaning dirt spawn dirt slime
  * [x] Dirt slime runs away
  * [x] Dirt slime can be killed
*   Items & Fun
  * [x] Bottle that breaks
  * [x] Mug
  *   Ladder for climbing
*   Goblin Attack
  *   Goblin NPC rigged and animated
  *   Goblin AI that walk to inn
    *   Goblins stay in group / group logic
  *   Goblins can attack player
  *   Goblins can attack customers / other NPCs
  *   Goblins die
    *   Pathfinding agent is exchanged for ragdoll
  *   Dead goblin can be burned / buried
  *   Pan attack / other kitchen weapons
    *   Unerring throw
  *   "No killing goblins" sign
*   Overall gameplay state tracking
  *   Track how much dirt there is in the inn
    *   much dirt affects customer happiness
  *   Track how much gold the player has earned
  *   Track customer happiness
  *   Display stats in ledger for innkeeper
*   Market
  *   player can use coins to buy additional items and or ingredients for inn
*   Saving
  *   player can save game
  *   player can start game from save
