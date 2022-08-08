# N-Queen-Visualizer

The N-queen problem is one of the most common and practical examples to understand Backtracking.

You are given an integer N. For a given N x N chessboard, find a way to place 'N' queens such that no queen can attack any other queen on the chessboard.

A queen can be attacked when it lies in the same row, column, or the same diagonal as any of the other queens. You have to print one such configuration.

Let’s take an example to understand the requirement.

Say, N=4. Now, we will try to place the 4 queens such that each of them is safe from every other queen.

There can be more than one such valid configuration. In this problem, our goal is just to print one of those.

The key idea is that no two queens can be placed in:

Same Row
Same Column
Same Diagonal
 
There are N rows, so we will place one queen in each row(as no two queens can be in the same column) such that they all are safe from each other.

We will use backtracking to solve the problem. It is a recursive approach in which we place the queen at a safe position and then recur for the remaining queens. If at any step the number of queens to be placed is not zero and there are no safe cells left, then we change the position of the previously placed queen and try another safe position.

Let’s see backtracking the approach step by step - 

Start with the first row.
Check the number of queens placed. If it is N, then return true.
Check all the columns for the current row one by one.
If the cell [row, column] is safe then mark this cell and recursively call the function for the remaining queens to find if it leads to the solution. 
If it leads to the solution, return true, else unmark the cell [row, column] ( that is, backtrack) and check for the next column.

If the cell [row, column] is not safe, skip the current column and check for the next one.
If none of the cells in the current row is safe, then return false.
