# GROKKING-NOTES

List of leetcode problems that are as close to grokking problems as possible. Thanks to https://gist.github.com/ysalau/c8cf5b5491ffcaf380b5241bf6876589

## Pattern: Sliding Window

The sliding window technique is a pattern for solving problems involving arrays or strings by keeping track of a window of elements that satisfies some condition, and moving the window through the array/string until all elements have been processed.

A common mnemonic for remembering the steps involved in using the sliding window technique is "SET", which stands for:

1.  S - Set up two pointers, left and right, that define the window.
2.  E - Expand the window (move the right pointer) until the condition is satisfied.
3.  T - Trim the window (move the left pointer) until the condition is no longer satisfied.

To help peg this information, imagine you are playing a game where you must find a treasure hidden inside a building. The building is represented by the array or string, and the two pointers represent the two doors of the room you are currently in. The goal is to find the room with the treasure by expanding and trimming the room until you find it.

To practice this technique, it is important to work through several examples and understand how the pointers move and the condition changes as you move through the array/string.

Here is a basic pseudocode template for sliding window algorithm:

```
start = 0
end = 0
while end < length_of_array:
    # expand the window if conditions are met
    while conditions_are_met(end):
        update_window_information(end)
        end += 1
    
    # shrink the window if conditions are not met
    while not conditions_are_met(end):
        update_window_information(start)
        start += 1

return result
```


## Pattern: Two Pointers

The Two Pointers technique is a method to solve certain types of problems efficiently. The idea behind this technique is to maintain two pointers, often referred to as left and right, that traverse the input array/string. The pointers move in opposite directions, and the purpose is to either find a target or to identify a valid subarray/substring.

Here is a template for the Two Pointers technique:

1.  Initialize two pointers, left and right, pointing to the start of the array/string
2.  While the left pointer is less than the right pointer:
    -   Check the condition to find the target or validate the subarray/substring
    -   If the condition is met, update the left or right pointer accordingly
3.  Return the result

To memorize this technique, you can use the mnemonic "LRL" (Left, Right, Left), which reminds you to first initialize the left and right pointers, then move the right pointer to the right and the left pointer to the left, and finally return the result.

You can also use the pegging technique, where you visualize the pointers as two pegs, and imagine them moving towards each other while checking the condition. This helps you remember the direction of movement and the purpose of the technique.

Here's a basic template for the Two Pointers technique in pseudocode:

```python
# two pointers, `left` and `right`, initially pointing to the start of the array
left = 0
right = 0

while right < len(array):
  # if the current subarray satisfies the condition, move `left` pointer towards the right
  while condition:
    # update some variables, e.g. sum or count
    update()
    left += 1

  # if the current subarray doesn't satisfy the condition, move `right` pointer towards the right
  # also update some variables, e.g. sum or count
  update()
  right += 1

# at this point, the optimal subarray that satisfies the condition is between `left` and `right-1`
return result

```
This is just a general outline of the Two Pointers technique, and you may need to modify the pseudocode based on the specific problem you're trying to solve. The main idea of Two Pointers is to use two pointers that move towards each other to maintain a valid subarray that satisfies some condition, and update the subarray whenever necessary.

To memorize this technique, you can use mnemonics and pegging. Mnemonics can help you remember key concepts and steps, while pegging can help you associate these concepts with specific objects or actions. For example, you can imagine the two pointers as two people holding a rope, and moving towards each other until they meet at the middle of the rope. The rope represents the subarray, and the meeting point represents the optimal solution. By using mnemonics and pegging, you can better retain the information and recall it more easily when you need it.


## Pattern: Fast & Slow pointers
The Fast & Slow Pointers technique is a pattern that uses two pointers to traverse through a list or an array. The fast pointer moves at a faster pace than the slow pointer, and the distance between them is used to determine the solution to a particular problem.

Here's a general template for using this technique:

1. Initialize two pointers, one fast and one slow, pointing to the beginning of the list.
2. Use a while loop to traverse the list, with the fast pointer moving at a faster pace than the slow pointer.
3. Use the distance between the fast and slow pointers to determine the solution to the problem.
4. Depending on the problem, you may also update the slow pointer as you traverse the list.
5. Continue the loop until the fast pointer has reached the end of the list.
6. Return the result based on the position of the slow pointer.

To memorize this technique using mnemonics and pegging, you can use the following:

Mnemonic: "FS - Follow the Speedy guy"
Pegging: Picture a slow hiker and a fast runner. The fast runner is ahead of the slow hiker and the hiker can determine how far ahead the runner is by counting their steps.

Pseudocode:

```python
Initialize two pointers, slow = 0, fast = 0
While fast < len(list):
  // update the fast pointer
  fast = fast + 1
  // update the slow pointer based on the problem requirements
  slow = updateSlow(slow)
Return result based on the position of the slow pointer
```


## Pattern: Merge Intervals

Merge Intervals technique is a useful technique when you have a set of intervals and you need to merge any overlapping intervals. Here's a template for the technique:

1.  Sort the intervals based on the start time
2.  Initialize a variable `result` with the first interval in the sorted list.
3.  Loop through the rest of the intervals and compare each interval with the last interval in `result`.
4.  If the current interval overlaps with the last interval in `result`, update the end time of the last interval in `result` to the maximum of the two end times.
5.  If the current interval does not overlap with the last interval in `result`, add it to `result`.
6.  Repeat steps 3-5 until all intervals have been processed.

Pseudocode:

```python
def merge(intervals):
  # sort intervals based on start time
  intervals.sort(key=lambda x: x[0])
  
  result = [intervals[0]]
  
  for i in range(1, len(intervals)):
    current_interval = intervals[i]
    last_interval = result[-1]
    
    # If the current interval overlaps with the last interval
    if current_interval[0] <= last_interval[1]:
      # update the end time of the last interval in result
      last_interval[1] = max(last_interval[1], current_interval[1])
    else:
      # If the current interval does not overlap with the last interval
      result.append(current_interval)
  
  return result

```

## Pattern: Cyclic Sort

Cyclic Sort is a technique used to sort elements in a cyclic manner. It is used when the elements in an array are in the range of 1 to n and there are no duplicates. The basic idea is to traverse the array and swap the elements to their correct position. Here is a template for the Cyclic Sort technique:

1.  Initialize a pointer "i" to traverse the array.
2.  Repeat the following steps as long as "i" is less than n: a. If the element at index "i" is not at its correct position, swap it with the element at its correct position. b. Increment the "i" by 1.

To memorize this technique, you can use the following mnemonic and pegging:

Mnemonic: CYCLE

-   C: Check the current element
-   Y: If it's Not Yet in its correct position
-   C: Cycle it to its correct position
-   L: And Loop to next position

Pegging: Picture a cycle spinning, with each element in its correct position. You can visualize yourself checking each element and if it's not in the right position, you move it to its correct position.

```python
function cyclicSort(arr):
  n = length of arr
  nums = arr
  i = 0
  
  while i < n:
    j = i
    while nums[j] != j + 1:
      swap(nums[j], nums[nums[j] - 1])
    i = i + 1
  
  return nums

function swap(a, b):
  temp = a
  a = b
  b = temp
```
The basic idea behind this technique is to iterate through the array and place each element in its correct position by swapping it with the element that is supposed to be in that position. The j variable is used to keep track of the correct position for the current element, and the inner while loop continues until the current element is in the correct position. The outer while loop continues until all elements have been placed in their correct positions.

## Pattern: In-place Reversal of a LinkedList

The template for In-place Reversal of a LinkedList technique is as follows:

1.  Initialize two pointers, one pointing to the head of the linked list, and the other pointing to null.
2.  Repeat the following steps until the first pointer reaches the end of the linked list: a. Save the next node of the first pointer in a variable. b. Update the next pointer of the first pointer to point to the second pointer. c. Move the second pointer to the first pointer. d. Move the first pointer to the saved next node.
3.  Update the head of the linked list to be the second pointer.

One mnemonic to help memorize this technique is "Head to Tail Flip". This refers to the process of flipping the direction of the pointers as they traverse the linked list from head to tail. The first pointer, moving through the linked list, represents the "head" while the second pointer represents the "tail". As they traverse the list, they "flip" the direction of the pointers, reversing the linked list.

A helpful pegging method to remember this technique could be to visualize yourself flipping a rope or a chain end over end, with each bead representing a node in the linked list. This visualization will help you understand how the pointers traverse the linked list and how they "flip" the direction of the pointers to reverse the linked list.

## Pattern: Tree Breadth First Search

The Tree Breadth First Search (BFS) technique is a way of traversing a tree in a level-by-level order, starting from the root node and visiting all the nodes on the current level before moving on to the next level.

Template:

1.  Initialize a queue to store the nodes to be visited
2.  Enqueue the root node
3.  While the queue is not empty: a. Dequeue a node from the queue and process it b. Enqueue the children of the processed node

Mnemonic: BFS can be remembered using the phrase "Breadth First, from the Start". This helps to emphasize the level-by-level nature of the traversal, starting from the root node.

Pegging: To further reinforce the concept, imagine a tree as a building with multiple floors. BFS would be like visiting each floor starting from the ground floor, visiting all the rooms on that floor before moving on to the next floor.


## Pattern: Tree Depth First Search

The Tree Depth First Search (DFS) technique is a tree traversal method that explores as far as possible along each branch before backtracking. DFS can be implemented using three methods: in-order, pre-order, and post-order. Each of these methods visits nodes in a different order, but all start from the root node and traverse each of the children nodes recursively.

To memorize DFS, you can use the mnemonic LDR for in-order DFS, DLR for pre-order DFS, and LRD for post-order DFS, where L represents visiting the left child, D represents visiting the current node, and R represents visiting the right child. To peg this mnemonic, you can visualize yourself moving through the tree and following the order of the letters.

The template for Tree Depth First Search (DFS) technique can be as follows:

```python
def dfs(node):
    if node is None:
        return
    # pre-order processing of the node
    # ...
    
    # recursive calls for the children of the node
    dfs(node.left)
    dfs(node.right)
    
    # post-order processing of the node
    # ...
```

To memorize this technique, one can use the following mnemonic: "DLR" (or "LDR"), which stands for "Depth-Left-Right" (or "Left-Depth-Right"). This mnemonic can be useful to remember the order in which the nodes of the tree are processed in the DFS approach. 


## Pattern: Two Heaps


## Pattern: Subsets


## Pattern: Modified Binary Search


## Pattern: Bitwise XOR


## Pattern: Top 'K' elements


## Pattern: K-way merge

## Pattern: 0/1 Knapsack

## Pattern: Topological Sort

