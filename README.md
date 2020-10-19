# Ants-Game--Based-off-Plants-vs.-Zombies-Game-
A game of Ants Vs. SomeBees consists of a series of turns. 
In each turn, new bees may enter the ant colony. Then, new ants are placed to defend their colony. 
Finally, all insects (ants, then bees) take individual actions. Bees either try to move toward the 
end of the tunnel or sting ants in their way. Ants perform a different action depending on their type, 
such as collecting more food, or throwing leaves at the bees. The game ends either when a bee reaches 
the end of a tunnel (you lose), or the entire bee fleet has been vanquished (you win).

Core concepts
The Colony. This is where the game takes place. The colony consists of several places that are chained together to form a tunnel where bees can travel through. The colony has some quantity of food that can be expended to deploy ant troops.

Places. A place links to another place to form a tunnel. The player can place a single ant into each place. However, there can be many bees in a single place.

The Hive. This is the place where bees originate. Bees exit the beehive to enter the ant colony.

Ants. Ants are the usable troops in the game that the player places into the colony. Each type of ant takes a different action and requires a different amount of food to place. The two most basic ant types are the HarvesterAnt, which adds one food to the colony during each turn, and the ThrowerAnt, which throws a leaf at a bee each turn. You will be implementing many more.

Bees. Bees are the antagonistic troops in the game that the player must defend the colony from. Each turn, a bee either advances to the next place in the tunnel if no ant is in its way, or it stings the ant in its way. Bees win when at least one bee reaches the end of a tunnel.

Core classes
The concepts described above each have a corresponding class that encapsulates the logic for that concept. Here is a summary of the main classes involved in this game:

GameState: Represents the colony and some state information about the game, including how much food is available, how much time has elapsed, where the QueenAnt resides, and all the Places in the game.
Place: Represents a single place that holds insects. At most one Ant can be in a single place, but there can be many Bees in a single place. Place objects have an exit to the left and an entrance to the right which are also places. Bees travel through a tunnel by moving to a Place's exit.
Hive: Represents the place where Bees start out (on the right of the tunnel).
AntHomeBase: Represents the place Ants are defending (on the left of the tunnel). If Bees get here, they win :(
Insect: A superclass for Ant and Bee. All insects have an armor attribute, representing their remaining health, and a place attribute, representing the Place where they are currently located. Each turn, every active Insect in the game performs its action.
Ant: Represents ants. Each Ant subclass has special attributes or a special action that distinguish it from other Ant types. For example, a HarvesterAnt gets food for the colony and a ThrowerAnt attacks Bees. Each ant type also has a food_cost attribute that indicates how much it costs to deploy one unit of that type of ant.
Bee: Represents bees. Each turn, a bee either moves to the exit of its current Place if no ant blocks its path, or stings an ant that blocks its path.
Game Layout
Below is a visualization of a GameState. As you work through the unlocking tests and problems, we recommend drawing out similar diagrams to help your understanding.
