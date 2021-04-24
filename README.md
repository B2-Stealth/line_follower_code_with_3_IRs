# Simple line follower code with 3 IRs

## Parts Used
Arduino Uno board, L239d motor driver, 3 IR sensors, jumper wires, and batteries

## Concepts
Arduino provides easy-to-use interfaces for complex electronic circuitry which makes it easier for a newbie to begin.

The basic principle behind the working of the line follower is that black is perfectly absorbent whereas any other color 
reflects upto some extent. So when the IR sensor is pointing towards a black material, it receives no returning signal, and the code is written to give 
appropriate responses
To simulate a turn, the rpm of one wheel is greater than that of the other.
To simulate an aggressive turn for sharp corners, the inner wheel rotates counter to the outer wheel.
Whereas normally, it is suffcient to ave it stationary.

NOTE-the rpm is set by using a tuple of 2 ints between 0 to 255, and must be set through extensive testing, for
     the best results.
