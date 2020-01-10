# NQueenJS
Visual representation/demo of NQueen Problem 

NOTE: Red Squares = Queen placement, when they disappear that means it was either placed in an invalid position or the position cannot be part of the final solution.

Problems Encountered and Lessons Learned: 
1. When running DOM manipulating code, browser would not update after every iteration of the recursive function.
When trying to change the color in the backtracking algorithm, it would update all squares at the end, which gave the final answer, but was not what I was
trying to achieve. My objective was to get the colors to update after each step to show that the algorithm worked to solving the N-Queen Problem.

Solution: JavaScript Execution and Page Rendering Occur at the same time
(setTimeout and clearTimeout)

"JavaScript execution and page rendering are done in the same execution thread, which means that while your code is executing the browser will not be redrawing the page."
To solve this problem, I created an array that would hold square objects that contained the name of the square and the color associated with it. I then made a function
to update the color of the square, while "yielding" control of the browser by using a setTimeout that executes a recursive call until I iterate through the whole array.


2. Backtracking Algorithm
This algorithm helps to solve problems that involve constraint satisfaction. The algorithm builds upon a solution, and removes a possibility if it no longer can be apart
of a valid solution.

For this specific problem, a Queen cannot be in the same row/column/diagonal as any other Queen. After checking that a position is valid, it places the queen, and does a recursive call on the next column to check if there is a valid position in that column. If there isn't a valid position in that column, that means a previous candidate is blocking/preventing a solution to be found so it needs to backtrack and remove the previous solution before continuing.

Link:   https://albertoe22.github.io/NQueenJS/

[Source](https://stackoverflow.com/questions/8110905/javascript-a-loop-with-innerhtml-is-not-updating-during-loop-execution)
