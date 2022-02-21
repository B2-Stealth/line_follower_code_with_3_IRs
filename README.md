# Line Follower

## Parts Used
Arduino Uno board, L239d motor driver, 3 IR sensors, jumper wires, and batteries

## Concepts
The basic principle behind the working of the line follower is that black is perfectly absorbent whereas any other color reflects upto some extent. Thus, when the IR sensor points towards a black material, it receives no returning signal, and the code is written to give 
appropriate responses.

To take a turn, the rpm of one wheel is greater than that of the other. To take an aggressive turn for sharp corners, the inner wheel rotates counter to the outer wheel, whereas normally, it would be suffcient to leave it stationary.

NOTE-the rpm, set by using a tuple of 2 ints between 0 to 255, must be chosen through extensive testing, for the best results.
