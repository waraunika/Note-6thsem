- **4 Hours**
- **7 Marks**
# Network Diagram
- Network diagrams are the preferred technique for showing activity sequencing
- a network diagram is a schematic display of the logical relationships among project activities
- two main formats are the arrow and precedence diagramming methods

## Arrow Diagramming Method
- AKA activity-on-arrow (AOA) network diagram
- activities are represented by arrows
- nodes or circles are the starting and ending points of activities
- can only show finish to start dependencies
- figure:
	- ![[Pasted image 20260406145422.png]]
## Precedence Diagramming Method
- PDM
- Activities show relationships between activities
- more popular than ADM and used used by project management software
- better at showing different types of dependencies
- figure:
	- ![[Pasted image 20260406145531.png]]
# Critical Path Method
- CPM is a network diagramming technique used to predict total project duration
- a critical path for a project is the series of activities that determines the earliest time by which the project can be completed.
- techniques for shortening schedules crashing activities and fast tracking activities
- the critical path is the longest path through the network diagram and has the least amount of slack or float
- slack or float is the least amount of time an activity can be delayed without delaying the project finish date
## Floats
- Total Float:
	- the amount of time an activity can be delayed without delaying the project completion date.
	- TF or float = Late Start - Early Start
		- or,
		- Late Finish - Early Finish
- Free Float
	- the amount of time that can be delayed without delaying the early start of any successor activity.
	- FF = Early start (of successor) - Early finish (of current)
		- or
		- FF = EF (current) - ES (previous) - duration
- Interfering float
	- total float - free float
## Pass
- Forward Pass
	- determines the early start and early finish dates for each activity
	- early finish = early start + duration
	- EF of predecessor = ES of successor
	- largest preceding EF at a merge point becomes ES for successor
- Backward Pass
	- Determines the late start and late finish dates
	- late start = late finish - duration
	- LS of successor = LF of predecessor
	- smallest succeeding LS at a burst point becomes LF for predecessor
- Figure:
	- ![[Pasted image 20260406150436.png]]