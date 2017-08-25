Changelog
==========

Summary:
--------
The changes made can be divided into 2 groups: Addition new variable in torcs
output, and implementation of LOOKAHEAD technique for steering.

First of all, currently simulator has little information about tracks and cars.
We added some variables for the simulator.

Lastly, we added basic technique for steering at curves. The car looks ahead
little bit and according to that, it steers to stay in the middle lane.


Per Commit
-----------

* e88ecf85514fc4545f59a19c7ae7ec5488532ea3
Add track friction variable to `torcs_output_name` in `data_list.h`. Furthermore
Put a proper value which is track friction (`tTrackSeg.surface->kFriction`) to
the track friction variable.

* 5db7e8233b1ba58f4cfed49c0de879206a190321
Implement LOOKAHEAD technique for the smooth steering. Function `getDistToSegEnd`
calcluates the distance between car and the end of a current track segment. 
Function `getTargetPoint` calculates the next point which the car must go. After
that we calculated the amount of steering using the current point and target 
point.

* a16b92e389881dbf5838265b3cedfc815ee09474
Change LOOKAHEAD parameters using heuristic. Still need to be improved.
