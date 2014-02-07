Bowling Kata
----

Notes
----
* A Game is made up of 10 frames
* A frame consists of 2* bowls (except the 10th frame _possibly_ having 3)
* During each bowl, the player has a chance to knock down 10 pins
* _Strike_: When all ten pins are knocked down with the first ball
* _Spare_: A "spare" is awarded when no pins are left standing after the second ball of a frame
* A game with all strikes will have 12 rolls
* A game with all gutterballs will have 20 rolls
* A game will have a maximum of 21 rolls if a third roll on the 10th frame is achieved

Scoring
----
* Strike
	* a player is awarded ten points, plus a bonus of whatever is scored with the next two balls
	```
	Frame 1, ball 1: 10 pins (strike)
	Frame 2, ball 1: 3 pins
	Frame 2, ball 2: 6 pins

	The total score from these throws is:
		Frame one: 10 + (3 + 6) = 19
		Frame two: 3 + 6 = 9
			TOTAL = 28
	```

	```
	Frame 1, ball 1: 10 pins (Strike)
	Frame 2, ball 1: 10 pins (Strike)
	Frame 3, ball 1: 9 pins
	Frame 3, ball 2: 0 pins (recorded as a dash '-' or '0' on the scoresheet)
		The total score from these throws is:
	Frame one: 10 + (10 + 9) = 29
	Frame two: 10 + (9 + 0) = 19
	Frame three: 9 + 0 = 9
		TOTAL = 57
	```
* Spare
	* A player achieving a spare is awarded ten points, plus a bonus of whatever is 
	scored with the next ball (only the first ball is counted)

	```
	Frame 1, ball 1: 7 pins
	Frame 1, ball 2: 3 pins (spare)
	Frame 2, ball 1: 4 pins
	Frame 2, ball 2: 2 pins
		The total score from these throws is:
	Frame one: 7 + 3 + 4 (bonus) = 14
	Frame two: 4 + 2 = 6
		TOTAL = 20
	```

The Kata Steps
----
* Create new solution
 	* **Client**: Bowl-O-Rama
	* **Project**: ScoreSheet
* Create "_domain_" Project
* Create "_test_" project
	* You know what to do

Domain Requirements
----
* This project will have a two classes: **GameScorer**, **Frame**
* GameScorer will have the following public methods:
	* ```void Roll(int numPinsFell)```
	* ```int GetScore()```
* Frame
	* ```void AddRoll(int numPinsFell)```
	* ```int PinsScored()```
	* ```Property: bool IsStrike```
	* ```Property: bool IsSpare```
	* ```Property: int Roll1``` - Note: Needed for testing
	* ```Property: int Roll2``` - Note: Needed for testing

The Tests
----
* Frame
	* ```AddRoll_CorrectlyAddsPinsToContainer```
	* TODO: More....
* ScoreSheet
	* _Note_: Sample scores will be in the following format ```2|5|X|5|/|...```
	* A game with all gutterballs should result in ==> 0
	* A game with all rolls knowking down 1 pin will result in ==> 20
	* Can handle spares Ex:
		* ```1|/|5|0.... ==> 20```
	* Can handle strikes Ex:
		* ```X|3|5|0.... ==> 26```
