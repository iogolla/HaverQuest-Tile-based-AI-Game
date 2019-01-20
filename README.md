[Link to the project specs](https://github.com/kmicinski/cs107-p8/blob/master/README.md)


# CS 107 Project 8 -- -- AI Adventure


In this project I'll be designing an AI implementation that solves a 
tile-based squirrel game. To present a clear process of my implementation,
I will divide my explanation into two parts. 

## Part 1: Getting to the Health Pack

This part will make the squirrel move to the health pack for the
purpose of building up more fuel. To make the squirrel move to the health pack, 
I will use the `Path Finder` class to develop a pathfinder solution. I will 
integrate its `findPath` method in my solution to make the squirrel 
move from the starting cordinate all the way to the health pack.

The methods I need to implement for this part are:

- (1) `getFuel(self)`, which reports the level of the fuel left
- (2) `move(self,x,y)`,  which accepts x and y in the range [-1,1] and 
moves to that tile using |x| + |y| fuel
- (3) `getHealthPacks(self)`, which gets the position of the healthpacks 
on the board 

In addition to these methods, I will add a field called `self.healthPack` 
to `MyAISquirrel` and set it to **None** then I will assign 
`getHealthPacks(self)` method to it so as to avoid losing 20 fuel each clocktick.
Before the first clocktick is called, I will make the squirrel move to the 
healthpack along the path generated by the `findPath` method from PathFinder class




# Part 2: Getting to the Exit Position

In this part, I will construct an AI that moves the squirrel from its 
current position all the way to the exit position while firing stones 
at the ferrets. This part will make the squirrel wait until the fuel builds up to 60 
before it makes any movement. The intention is to make it gather enough fuel so that 
it can be able to self-sustain itself through the exit without losing fuel whenever 
it gets hit by a stone fired by the ferrets. Initially, the squirrel will move horizontally
toward the left without firing a single stone but once it starts moving vertically, 
it will start firing stones up and diagonally toward the northwest direction
in attempt to kill the ferrets. 

The methods I need to implement for this part are:

- (1) `getExit(self)`, which reports the position of the exit tile
- (2) `move(self,x,y),  which accepts x and y in the range [-1,1] and 
moves to that tile using |x| + |y| fuel
- (3) `fireStone(self,x,y`, which fires a stone with a set speed along
the vector (x * speed, y * speed). You don't have any control over speed, 
but x and y must be in the range [-1,1]

In addition to these methods, I will add a field called `self.exitPosition` 
to `MyAISquirrel` and set it to **None** then I will assign 
`getExit(self)` method to it so as to avoid losing 30 fuel each clocktick


