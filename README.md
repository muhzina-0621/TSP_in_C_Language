<h1 align="center" id="title">TSP Program in C Language</h1>



<h2>💖Like my work?</h2>

This code implements a solution to the Traveling Salesman Problem (TSP) using dynamic programming. Here's a breakdown of the underlying method:  
  
Initialization:  
n: Number of cities.  
cost\[MAX\_N\]\[MAX\_N\]: Cost matrix representing the cost of traveling between cities.  
dp\[1 << MAX\_N\]\[MAX\_N\]: Dynamic programming table to store intermediate results.  
dp\[mask\]\[pos\] represents the minimum cost starting from city pos visiting all cities indicated by the bitmask mask.  
  
Recursive Function tsp(mask pos):  
Base Case:  
If all cities have been visited (i.e. mask == (1 << n) - 1) return the cost of returning to the starting city (cost\[pos\]\[0\]).  
Memoization: Check if the solution for the current state (mask pos) has been previously calculated. If yes return the cached result.  
Exploration: Iterate through all cities (next) that have not been visited yet (indicated by (mask & (1 << next)) == 0).  
Recursion: For each unvisited city calculate the cost of visiting it (cost\[pos\]\[next\]) and recursively call tsp with updated state (mask | (1 << next) next).  
Update the minimum cost (ans) if a better solution is found.  
Store the minimum cost for the current state (mask pos) in the dynamic programming table dp.  
Main Function main():  
Input: Prompt the user to input the number of cities (n) and the cost matrix representing the distances between cities.  
Memory Initialization:  
Initialize the dynamic programming table dp with -1 using memset.  
Execution:  
Call the tsp function with the starting state (1 0) where 1 represents the starting city and 0 represents the position of the starting city.  
Output:  
Print the minimum cost of the TSP tour.  
This method effectively solves the TSP by using dynamic programming to avoid redundant calculations of subproblems significantly reducing the time complexity compared to naive recursive approaches.
