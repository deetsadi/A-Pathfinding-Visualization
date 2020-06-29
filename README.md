# AStar Pathfinding Visualization
This program will find the shortest distance between two points on a maze by utilizing the A* pathfinding algorithm. This path will then be displayed on a map of the maze to help provide a visual representation of the solution.

# Instructions:
1. Ensure that the matplotlib, tkinter and numpy modules are installed. 
   If not, install using this command:
   ```pip install matplotlib tkinter numpy```
2. The maze uses 0 to represent an free square and 1 to represent a wall. It can be modified if you want. 
3. Run the program and the solution will be visually represented on a diagram.

# How it works
The AStar Pathfinding algorithm works slightly differently than other similar algorithms, such as the breadth first search. This is because AStar works to combine 2 other algorithms together: the Best-First Search and Djkastra's algorithm. This allows the algorithm to use a heuristic to guide itself but also find the shortest path possible.

AStar utilizes the formula f(n) = h(n) + g(n) when choosing where to move next in a given problem. g(n) is the "cost" to move to a certain position, calculated by looking at the number of vertices/squares that must be crossed to reach the next possible grid square. In most cases where the algorithm can only move along one grid square each move, this cost is the same for each move and is therefore a constant that does not affect the decision making. h(n) is calculated by creating a right angle triangle between the current grid square and goal square and then finding the length of the hypotenuse. This helps to accurately find which moves will lead to the fastest solution. The combination of these two functions is what differentiates AStar from other pathfinding algorithms as it does not pursue ineffective paths and instead favours options which will find the goal faster. 

Since any position in the maze can have up to 8 possible moves, AStar will first see which moves are possible. Next, f(n) will be calculated for each of these possible options, and the moves that will result in a lower value than the current Node (moves that will bring the algorithm closer to the goal) will added to an open_list to evaluate individually. In this way, the algorithm is able to branch out and move closer to the objective. 
