# A* and JPS Pathfinding Game
## Overall Design

__The main pathfinding algorithms used is A star and Jump Point Search__
__It can be changed by adjusting the value of mode. 0 is using A* and any other value is using JPS__

Build a 3D space as shown in the sketch below. The area is roughly rectangular, with an upper mezzanine level. It is divided into two sections, with the two sections of each level connected by 3 bridges (2 sloped) as shown. These bridges should be not quite wide enough to allow 2 characters to pass each other, so only one character can cross a given bridge at a time. Position the camera and use relatively even lighting to allow easy visual observation of as much of the entire level as possible.

![image](https://user-images.githubusercontent.com/68981504/148135251-7bae8401-4f1d-4d90-9b32-624b1f7a30b2.png)

Connection between the lower and upper levels is also possible through 2 transporters. Each can transport up to 3 NPCs at a time. Simulate the effect by teleporting characters from the lower to upper or vice versa. Define a perimeter/waiting area in front of the transporter in both the lower and upper parts. Each waiting area should easily hold at least 3 NPCs. Transporters then operate following a fixed schedule that cycles between moving NPCs from the lower level to the upper and then reversing direction: 

(1) up to 3 waiting NPCs are selected and removed from the lower (upper) waiting area; 

(2) transportation between levels takes 1s; 

(3) the NPCs being transported are re-spawned in the waiting area of the upper (lower) level as other NPCs are removed from the upper (lower) waiting area to repeat the process in the opposite direction.

The walkable area have 10 small, randomly placed (different on each gameplay) and non-overlapping obstacles. Obstacle boundaries are simple geometric shapes, but with some variation in either shape or orientation.

Populate the area with n NPCs, where n is a simulation (editor) parameter. NPCs are spawned at random, non-overlapping, locations anywhere in the non-obstacle game space, but not in the waiting areas. Each NPC follows the same rote behaviour, consisting of repeatedly doing the following: 

(1) choose a random destination (any non-obstacle location other than the waiting areas, and ignoring other NPCs) 

(2) make a plan to move to it and follow it, 

(3) pause for 200–1000ms once they arrive.

Implemented two different pathfinding algorithms A Star and Jump Point Search here.
