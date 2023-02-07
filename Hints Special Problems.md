# Cheetcode Special Problems Summary and Hint

## Valid Palindrome
https://leetcode.com/problems/valid-palindrome/ 
-   Problem: Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.
-   Hint: Two pointer approach can be used to compare characters from start and end of the string.

## Valid Palindrome II

https://leetcode.com/problems/valid-palindrome-ii/

-   Problem: Given a non-empty string s, you may delete at most one character. Judge whether you can make it a palindrome.
-   Hint: Use two pointers approach, if the characters at both pointers are not the same, then delete one of them and check if the resulting string is a palindrome.

## Kth Largest Element in an Array
https://leetcode.com/problems/kth-largest-element-in-an-array/

-   Problem: Find the kth largest element in an unsorted array.
-   Hint: QuickSelect or Heap can be used to solve this problem efficiently.

## Serialize and Deserialize Binary Tree
https://leetcode.com/problems/serialize-and-deserialize-binary-tree/

-   Problem: Serialize and deserialize a binary tree.
-   Hint: Use pre-order traversal to serialize and deserialize the tree.

## Add Binary
https://leetcode.com/problems/add-binary/
-   Problem: Given two binary strings, return their sum (also a binary string).
-   Hint: Start from the end of the strings and keep a carry to store any overflow from the addition.

## Read N Characters Given Read4 II - Call multiple times
https://leetcode.com/problems/read-n-characters-given-read4-ii-call-multiple-times/
-   Problem: Given a file and assume that you can only call a function `read4` which reads 4 characters at a time from the file. Implement a function to read n characters.
-   Hint: Use a buffer to store characters read from the file using `read4` function, and keep track of the current position and remaining characters.

## Decode String
https://leetcode.com/problems/decode-string/
-   Problem: Given an encoded string, return its decoded string.
-   Hint: Use a stack to keep track of the characters and numbers, and use recursion to solve the problem.


## Shortest Path in a Grid with Obstacles Elimination
https://leetcode.com/problems/shortest-path-in-a-grid-with-obstacles-elimination/

-   Problem: Given a m * n grid, find a path from the top-left to the bottom-right with the smallest number of moves. You can eliminate at most k obstacles.
-   Hint: Use BFS to solve this problem.

## K Closest Points to Origin
https://leetcode.com/problems/k-closest-points-to-origin/

-   Problem: Given a list of points on the 2D plane, find the K closest points to the origin (0, 0).
-   Hint: Use quick select or heap to solve this problem.

## Dot Product of Two Sparse Vector
https://leetcode.com/problems/dot-product-of-two-sparse-vectors/

-   Problem: Given two sparse vectors, compute their dot product.
-   Hint: Use a dictionary to store the non-zero elements of the sparse vectors and calculate the dot product.
- 
## Sparse Matrix Multiplication
https://leetcode.com/problems/sparse-matrix-multiplication/
-   Problem: Given two sparse matrices A and B, return the result of AB.
-   Hint: Use a nested loop to calculate the result of AB, and store only the non-zero elements in the resulting matrix.

## Divide Two Integers

https://leetcode.com/problems/divide-two-integers/

-   Problem: Given two integers dividend and divisor, divide two integers without using multiplication, division, and mod operator.
-   Hint: Use bit shifting and subtraction to perform the division.

## LRU Cache
https://leetcode.com/problems/lru-cache/
-   Problem: Design and implement a data structure for LRU (Least Recently Used) cache.
-   Hint: Use a doubly linked list and a hash map to implement the LRU cache.

## Monotonic Array
https://leetcode.com/problems/monotonic-array/

-   Problem: Given an array A, return true if and only if the given array A is monotonic. An array is monotonic if it is either monotone increasing or monotone decreasing.
-   Hint: Iterate through the array and keep track of the direction (increasing or decreasing) of the elements. If the direction changes, return False.
-   Time complexity: O(n)
-   Space complexity: O(1)


## Candy Crush
https://leetcode.com/problems/candy-crush/

-   Problem: Given a 2D integer array board, candy crush game rules are applied repeatedly until no more moves are possible. The rules are: if 3 or more candies of the same type are adjacent vertically or horizontally, "crush" them all at the same time - these positions become empty.
-   Hint: Start from the bottom-right corner and work your way up to the top-left corner.
-   Time complexity: O(n^2)
-   Space complexity: O(n^2)

## Letter Combinations of a Phone Number
https://leetcode.com/problems/letter-combinations-of-a-phone-number/
-   Problem: Given a string containing digits from 2-9, return all possible letter combinations that the number could represent.
-   Hint: Use a backtracking approach.
-   Time complexity: O(3^n * 4^m), where n is the number of digits in the input that maps to 3 letters (e.g. 2, 3, 4, 5, 6, 8) and m is the number of digits in the input that maps to 4 letters (e.g. 7, 9).
-   Space complexity: O(3^n * 4^m)

## Asteroid Collision
https://leetcode.com/problems/asteroid-collision/

-   Problem: Given an array asteroids of integers, return the state of the asteroids after all collisions.
-   Hint: Use a stack to keep track of the state of the asteroids.
-   Time complexity: O(n)
-   Space complexity: O(n)

## Time-based Key-Value Store
https://leetcode.com/problems/time-based-key-value-store/

-   Problem: Create a time-based key-value store class TimeMap, that supports two operations.
    -   set(string key, string value, int timestamp)
    -   get(string key, int timestamp)
-   Hint: Use a dictionary to store the values for each key, and a binary search to find the correct value for a given key and timestamp.
-   Time complexity: O(log n) for the binary search operation.
-   Space complexity: O(n)

## Number of Provinces
https://leetcode.com/problems/number-of-provinces/

-   Problem: Given a 2D grid of characters representing a province, find the number of distinct provinces. A province is defined as a region of connected characters with the same character.
-   Hint: Use a depth-first search or a union-find algorithm to find the number of connected regions.
-   Time complexity: O(n^2) for the depth-first search or O(n^2) for the union-find algorithm.

## valid-parentheses
https://leetcode.com/problems/valid-parentheses/

-   Problem: Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.
-   Hint: Using a stack to keep track of the last opening parenthesis. Whenever a closing parenthesis is encountered, pop the last opening parenthesis from the stack and check if they match. If they don't match or if the stack is empty, return false.
-   Time complexity: O(n), where n is the length of the input string.
-   Space complexity: O(n)

## product-of-array-except-self
https://leetcode.com/problems/product-of-array-except-self/


-   Problem: Given an array of n integers where n > 1, return an array output such that output[i] is equal to the product of all the elements of nums except nums[i].
-   Hint: You can compute the products from left to right and then from right to left in two separate arrays. Finally, combine these two arrays to obtain the final result.
-   Time complexity: O(n)
-   Space complexity: O(n)

## string-compression
https://leetcode.com/problems/string-compression/

-   Problem: Implement a method to perform basic string compression using the counts of repeated characters.
-   Hint: Keep a count of the current character and append it to the result string along with its count whenever the next character is different or when you have reached the end of the input string.
-   Time complexity: O(n)
-   Space complexity: O(n)

## design-hit-counter

https://leetcode.com/discuss/interview-question/178662/Design-a-Hit-Counter/

https://leetcode.com/discuss/interview-question/615505/Google-or-Onsite-or-Design-Hit-Counter

- Problem Statement: Design a hit counter which counts the number of hits received in the past 5 minutes.

- Hint: An array of size 300 (since each slot corresponds to a second, and there are 300 seconds in 5 minutes) can be used to store the number of hits in each second. To get the current number of hits, simply sum the values in the array. To update the counter, increment the value at the current second modulo 300.

- Time Complexity: O(1) for each hit.

- Space Complexity: O(1) since the size of the array is fixed.


## Logger Rate Limiter
https://leetcode.com/problems/logger-rate-limiter/

Problem Statement: Design a logger system that receive stream of messages along with its timestamps, each message should be printed if and only if it is not printed in the last 10 seconds.

Hint: A hashmap that stores the message and its last timestamp can be used to determine if a message is to be printed or not. The time complexity to store a message is O(1), and the time complexity to retrieve a message is O(1) as well.

Time Complexity: O(1) for each message.

Space Complexity: O(n) where n is the number of unique messages that have been logged so far.

## Game of Life
https://leetcode.com/problems/game-of-life/

-   Problem Statement: Given a board containing `m x n` cells, each cell has an initial state, live (represented by 1) or dead (represented by 0). The game is to implement the rules of life and determine the next state of the board after one update.
-   Hint: One approach is to use an extra board to simulate the game, another approach is to use a 2-bit number to represent the current state and next state of a cell in the same number.
-   Time Complexity: O(mn) where m is the number of rows and n is the number of columns.
-   Space Complexity: O(mn)

## Basic Calculator II
https://leetcode.com/problems/basic-calculator-ii/

-   Problem Statement: Implement a basic calculator to evaluate arithmetic expressions containing only `+`, `-`, `*`, and `/`.
-   Hint: One approach is to use a stack to keep track of numbers and operators and perform the calculation from left to right. Another approach is to split the expression into tokens and use a recursive function to evaluate them.
-   Time Complexity: O(n) where n is the length of the expression.
-   Space Complexity: O(n) where n is the length of the expression.
