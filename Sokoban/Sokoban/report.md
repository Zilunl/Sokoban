# Deadlock and Optimizations

Explain your optimizations if applicable

My optimizations code in the last two function in utils.c
->bool dead_square_deadlock(sokoban_t* init_data, state_t* state);
->bool square_check(int x, int y, sokoban_t* init_data, state_t* state);

I try to implement Dead square deadlocks
I choose this deadlock because a box on one of these squares will always result in a simple deadlock

If the player pushed the box one square up, the box would still be pushable (to the left and right), 
but no matter what the player does, it won't be possible to push the box to the goal anymore.

I try to solve it by
- find the next one if it is a box
- find the next one of box if it is a wall
- loop all maps, for example:
	- if the player at (x, y)
	- the box at (x, y+1n
	- and (x, y+2) is a wall
	- loop all the maps which has the same y coordinate of box(y+1), at same horizontal line
	- if there is no map has the same y coordinate, the game has deadlocked
	- because now the box only can move left or right, but there is no goal at left or right, so it fails.


