#Turtles all the Way Down
###This repo contains preliminary sketches and design explanations of a set-theory proof game

Users are first brought to a login/signup page which has not yet been designed.

###Level Selection

After logging in, Users are brought to the following level selection page:

![level selection page](./images/levelSelect.jpg)


###The Game
After selecting a level, users are brought to the main game page, which has three distinct sections:

1. The Universe
	* The list of all sets (represented as boxes) and non-set elements in existence
	* Takes up the left third(ish) of the screen
2. The Creation/Exclamation area
	* Users can drag sets into this area to create new sets/elements,and to assert, or assume that a prestablished thing is an element, or is not an element of a set
	* Takes up the middle third(ish) of the screen
3. The Turtle Map
	* Users can use this to keep track of the logical structure they are implementing
	* Logical Propositions are represented as turtles, with the statement written on their shell
	* Players must navigate from the assumption turtles at the top to the conclusion turtles at the bottom with a series of assertions (new turtles)
	* Takes up the right third(ish) of the screen
![game overview](./images/gameOverview.jpg)

###The Universe
* The universe is divided into a section for stets, represented as boxes, and elements (non-sets), represented as various animals
* Each set has a series of syntactic equivalences that can be substituted for the set
	* These can be literal lists of elements:
		* {x, y, z}
	* They can also be operations between other sets:
		* A **INTERSECT** B
		* A U B
		* A/B
		* A'(The compliment of A)
	* Ideally, they can even be subset notation:
		* {x in A | x is a tiger}
	* Each set has exactly one syntactic formulation (of the ones proven to be the same) that is *active* at a time
		* Clicking on a set creates a dropdown menu of its proven semantically equivalent syntactic formulations; choosing one makes it the *active* formulation
		* When a user tries to claim that something is contained, or not contained in a given set, A, they claim it specifically for the *active* formulation
		* Each kind (literal, union, intersect, subset, etc) of formulation carries with it a specific grounds upon which you can claim that a given element is in that set, or not in it
			* These are used in the Exclamatory zone to create new propositions that fill the turtle map
	* Hovering on a set displays green lines to all elements (and sets) that are known to be contained in the hovered set, and red lines to all elements and sets known not to be in the hovered set
* Hovering an element displays green lines to all sets known to contain it, and red lines to all sets known not to contain it
* Two sketches of the universe:
![Universe Set Close Up](./images/universeSet.jpg)
![Universe Element Close Up](./images/universeElement.jpg)

###The Turtle Map
* The turtle map displays the logical structure of the proof
* Based on the structure of the claim (set inclusion, set equality, element contained in set, etc), assumptions are placed at the top of the map, and the logically necessary conclusion steps are placed at the bottom
	* For set equality, The map is split in two at the very beginning. One path assumes there is an element of the left, and concludes it to be in the right, the other does the opposite
		* Both paths must end with the conclusion that the given element is a member of the other set, so this is provided, also
		* The user must make assertions (new turtles) to bridge the gap from the assumptions, to the conclusion

Here is a sketch of the logical structure of a proof of the claim: A U B = B U A:
![Proof Structure](./images/proofStructure.jpg)

And Here is the equivalent structure where the assumptions are reduced to points (these will be turtles in the actual map, with the propositions written on the shells)
![Turtle Map](./images/turtleMap.jpg)
