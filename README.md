# GROKKING-NOTES


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
The Two Heaps technique is a method for solving problems where we need to maintain a dynamic window of elements in a sorted or partially sorted order. This technique uses two heaps to maintain the elements: a max-heap and a min-heap. The max-heap stores the elements that are greater than or equal to the median, while the min-heap stores the elements that are less than the median. By maintaining these two heaps, we can efficiently find the median, add or remove elements, and keep the windows in a partially sorted order.

Mnemonic: "Max-Heap Min-Heap Median" (MMM)

Pegging: Imagine two buckets, one filled with elements greater than or equal to the median (max-heap) and one filled with elements less than the median (min-heap). The median is like the dividing line between the two buckets.

Pseudocode:

```python
1. Create two heaps: maxHeap and minHeap
2. Maintain the size of maxHeap to be greater than or equal to minHeap
3. Whenever a new element is added, add it to maxHeap and then balance the size of the two heaps if necessary
4. To find the median, check the size of the two heaps. If maxHeap has more elements, return its maximum element, otherwise return the minimum element of minHeap
5. To remove an element, remove it from the heap that contains it
6. Rebalance the size of the two heaps if necessary
```

## Pattern: Subsets

The Subsets technique is a method used to find all the possible subsets of a set. To implement this, we can use either Backtracking or Bit Manipulation.

Mnemonic: "SEB" (Select, Explore, Backtrack)
Pegging: To help remember this technique, think of a set of items as a treasure chest, and each subset as a bag you can put items in. When exploring a set, you have two options - select an item to put in the bag or skip the item. When you have explored all the items, you backtrack to the previous item and make a different decision.

Pseudocode for backtracking:

```python
result = []
def subsets_helper(start, subset, nums):
  result.append(subset)
  for i in range(start, len(nums)):
    subsets_helper(i + 1, subset + [nums[i]], nums)

def subsets(nums):
  subsets_helper(0, [], nums)
  return result

```

## Pattern: Modified Binary Search

The Modified Binary Search technique is used to search for a target element in a sorted array, where the array may have a condition that makes it difficult to determine if a given middle element is the correct answer. To use this technique, you need to modify the standard binary search algorithm in a way that takes into account the additional condition.

And here's a simple pegging exercise to help you recall the technique:

-   Picture a set of shelves in your mind, where each shelf has a number of books on it.
-   Imagine you're looking for a specific book, but the shelves are arranged in a way that makes it difficult to determine which shelf the book is on.
-   In this situation, you would use the Modified Binary Search technique to find the book by making educated guesses and checking each shelf until you find the right one.
-   Repeat the process a few times in your mind to reinforce your memory of the technique.

```python
function binarySearch(arr, target):
    left = 0
    right = len(arr) - 1

    while left <= right:
        mid = left + (right - left) // 2

        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1

    return -1

```

To memorize this, you can use the mnemonic "Less to More" to remember that when the target value is greater than the current value at the middle index, you need to search in the right half of the array (the values are increasing). If the target value is less than the current value, you need to search in the left half of the array.

## Pattern: Bitwise XOR
The Bitwise XOR technique is a mathematical operation that can be used to solve various computer science problems, such as finding the missing number in an array or finding the single non-duplicated number in an array.

To memorize the Bitwise XOR technique, you can use the following mnemonic and pegging:

Mnemonic: XOR (Exclusive OR) Pegging: Think of the XOR operation as a way to "cancel out" pairs of matching numbers.

Pseudocode:

```python
result = 0
for each number in the array:
    result = result XOR number
return result
```

In this pseudocode, the result is initially set to 0, and for each number in the array, it performs the XOR operation with the result. The XOR operation will cancel out pairs of matching numbers and return the single non-duplicated number in the end.

## Pattern: Top 'K' elements
The Top 'K' elements technique is a method used to find the k largest or k smallest elements in a given data set. There are several algorithms to achieve this, including Heap, QuickSelect, and Counting Sort.

To memorize this technique using mnemonics and pegging, you can use the following mnemonic: "KTOP" (K Thorough Ordering Process)

Pseudocode for finding k largest elements using a Min Heap:

1.  Create a Min Heap with a capacity of k elements
2.  Traverse the entire data set and for each element:
    -   If the heap size is less than k, insert the element into the heap.
    -   If the heap size is equal to k, compare the element with the minimum element in the heap. If the element is larger, remove the minimum element and insert the current element.
3.  The k largest elements are now stored in the heap.

Pseudocode for finding k smallest elements using a Max Heap:

1.  Create a Max Heap with a capacity of k elements
2.  Traverse the entire data set and for each element:
    -   If the heap size is less than k, insert the element into the heap.
    -   If the heap size is equal to k, compare the element with the maximum element in the heap. If the element is smaller, remove the maximum element and insert the current element.
3.  The k smallest elements are now stored in the heap.


The "Top 'K' Elements" technique is used to find the k largest or smallest elements in a given collection (such as an array or list). One common way to solve these types of problems is to use a Min Heap of size k to keep track of the k largest elements.

Here is a sample python code that demonstrates this approach:

```python
import heapq

def top_k_elements(nums, k):
    min_heap = []
    for num in nums:
        if len(min_heap) < k:
            heapq.heappush(min_heap, num)
        else:
            if num > min_heap[0]:
                heapq.heapreplace(min_heap, num)
    return min_heap

# Example usage
nums = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
k = 4
print(top_k_elements(nums, k))
# Output: [5, 5, 5, 9]
```
In this code, we use the heapq library in python to create a Min Heap and manipulate it. The function heappush is used to insert elements into the heap, and the function heapreplace is used to replace the smallest element in the heap with a new element if it is larger. In this way, the heap will always contain the k largest elements in the input nums array.


## Pattern: K-way merge

The K-way merge technique is a way to merge multiple sorted arrays or lists into a single sorted array. The approach is to keep a pointer for each of the arrays, and iteratively pick the smallest element among the elements pointed by all the pointers, add it to the result array and move the pointer of the corresponding array forward.

To memorize this technique, you can use the mnemonic "PKM" (Pick, Keep, Move), to remember the three main steps of the algorithm:

1.  Pick the smallest element among the elements pointed by all the pointers.
2.  Keep the result array sorted.
3.  Move the pointer of the corresponding array forward.

You can also use the pegging technique, where you associate each step of the algorithm with a physical action. For example, you can associate "pick" with pointing your index finger, "keep" with holding your hand in front of you, and "move" with moving your hand forward. By performing these physical actions, you can help fix the steps of the algorithm in your memory.

Here is a sample Python code to help you memorize the K-way merge technique:

```python
from heapq import heappush, heappop

def merge_k_sorted_arrays(arrays):
    result = []
    min_heap = []
    for i, array in enumerate(arrays):
        heappush(min_heap, (array[0], i, 0))
        
    while min_heap:
        value, array_index, element_index = heappop(min_heap)
        result.append(value)
        
        if element_index + 1 < len(arrays[array_index]):
            heappush(min_heap, (arrays[array_index][element_index + 1], array_index, element_index + 1))
            
    return result

```

You can use the mnemonic "K-MART" to remember the steps involved in K-way merge:

-   **K** stands for "K arrays"
-   **M** stands for "Merge"
-   **A** stands for "Array"
-   **R** stands for "Result"
-   **T** stands for "Top (element from the min heap)"

So, the mnemonic helps you remember that you need to merge K arrays to get the result by keeping the top element from the min heap.

## Pattern: Topological Sort

Topological sort is a linear ordering of the vertices of a directed acyclic graph (DAG) such that for every directed edge (u, v), vertex u comes before vertex v in the ordering. This technique is used in scheduling problems and to find dependencies between tasks.

A mnemonic to help remember the Topological Sort technique is: "Task Ordering" - thinking about tasks that need to be done in a specific order, like a to-do list.

Pegging technique can be used to associate the concept with a real-world scenario, such as the tasks involved in planning a trip, where each task depends on the completion of another task. For example, you can't book a flight until you have decided on a destination, and you can't rent a car until you have booked a flight.

Here is sample python code for Topological Sort:

```python
from collections import defaultdict

class Graph:
  def __init__(self, vertices):
    self.graph = defaultdict(list)
    self.V = vertices

  def addEdge(self, u, v):
    self.graph[u].append(v)

  def topologicalSortUtil(self, v, visited, stack):
    visited[v] = True
    if v in self.graph.keys():
      for node in self.graph[v]:
        if visited[node] == False:
          self.topologicalSortUtil(node, visited, stack)
    stack.append(v)

  def topologicalSort(self):
    visited = [False] * self.V
    stack =[]
    for i in range(self.V):
      if visited[i] == False:
        self.topologicalSortUtil(i, visited, stack)
    print(stack[::-1])

g= Graph(6)
g.addEdge(5, 2);
g.addEdge(5, 0);
g.addEdge(4, 0);
g.addEdge(4, 1);
g.addEdge(2, 3);
g.addEdge(3, 1);

print("Topological sort of the given graph is: ")
g.topologicalSort()

```

You can use mnemonics to remember the steps of Topological Sort. For example: "TV Show", where T stands for "Topological sort", V stands for "Visit nodes", and S stands for "Store the result in a stack". The order of these steps can be remembered using the mnemonic: "TV Show".
