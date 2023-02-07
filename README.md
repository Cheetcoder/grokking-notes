# GROKKING-NOTES

List of leetcode problems that are as close to grokking problems as possible.

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

* Couldn't find equivalent for the first question. The second question below encompasses the first one though. See https://leetcode.com/problems/missing-number/discuss/859510/C%2B%2B-O(N)-O(1)-using-Cyclic-Sort for how grokking the coding interview approached these problems. It uses the fact that we can sort the array in O(n) without comparison operators
* https://leetcode.com/problems/missing-number/
* https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/
* https://leetcode.com/problems/find-all-duplicates-in-an-array/
* combine https://leetcode.com/problems/find-the-duplicate-number/ and https://leetcode.com/problems/missing-number/
* https://leetcode.com/problems/first-missing-positive/
* https://leetcode.com/problems/kth-missing-positive-number/

## Pattern: In-place Reversal of a LinkedList
* https://leetcode.com/problems/reverse-linked-list/
* https://leetcode.com/problems/reverse-linked-list-ii/
* https://leetcode.com/problems/reverse-nodes-in-k-group/
* Next question is the same, but alternate each subgroup
* https://leetcode.com/problems/rotate-list/

## Pattern: Tree Breadth First Search
* https://leetcode.com/problems/binary-tree-level-order-traversal/
* https://leetcode.com/problems/binary-tree-level-order-traversal-ii/
* https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/
* https://leetcode.com/problems/minimum-depth-of-binary-tree/
* https://leetcode.com/problems/inorder-successor-in-bst/  # Close, not exact
* https://leetcode.com/problems/populating-next-right-pointers-in-each-node/  # Close, grokk assumes non-perfect tree
* Next question is the same, but connect end nodes to the next level instead of null
* https://leetcode.com/problems/binary-tree-right-side-view/

## Pattern: Tree Depth First Search
* https://leetcode.com/problems/path-sum/
* https://leetcode.com/problems/path-sum-ii/
* https://leetcode.com/problems/sum-root-to-leaf-numbers/
* https://leetcode.com/problems/check-if-a-string-is-a-valid-sequence-from-root-to-leaves-path-in-a-binary-tree/description/
* https://leetcode.com/problems/path-sum-iii/
* https://leetcode.com/problems/diameter-of-binary-tree/
* https://leetcode.com/problems/binary-tree-maximum-path-sum/

## Pattern: Two Heaps
* https://leetcode.com/problems/find-median-from-data-stream/
* https://leetcode.com/problems/sliding-window-median/
* https://leetcode.com/problems/ipo/
* https://leetcode.com/problems/find-right-interval/

## Pattern: Subsets
* https://leetcode.com/problems/subsets/
* https://leetcode.com/problems/subsets-ii/
* https://leetcode.com/problems/permutations/
* https://leetcode.com/problems/letter-case-permutation/
* https://leetcode.com/problems/generate-parentheses/
* https://leetcode.com/problems/generalized-abbreviation/
* https://leetcode.com/problems/different-ways-to-add-parentheses/
* https://leetcode.com/problems/unique-binary-search-trees-ii/
* https://leetcode.com/problems/unique-binary-search-trees/

## Pattern: Modified Binary Search
* https://leetcode.com/problems/binary-search/  # Close enough. The grokking problem allows sorted input arrays as ascending or descending, which only introduces a simple check
* Did not find. Problem is find index of smallest element greater or equal to input value
* https://leetcode.com/problems/find-smallest-letter-greater-than-target/
* https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/
* https://leetcode.com/problems/search-in-a-sorted-array-of-unknown-size/
* https://leetcode.com/problems/find-k-closest-elements/ (with K == 1)
* https://leetcode.com/problems/peak-index-in-a-mountain-array/
* https://leetcode.com/problems/find-in-mountain-array/
* https://leetcode.com/problems/search-in-rotated-sorted-array/
* Similar to previous, but find the number of rotations of the array.

## Pattern: Bitwise XOR
* https://leetcode.com/problems/single-number/
* https://leetcode.com/problems/single-number-iii/
* https://leetcode.com/problems/complement-of-base-10-integer/
* https://leetcode.com/problems/flipping-an-image/

## Pattern: Top 'K' elements
* Same as second question, but the first Grokking question wants the top K instead of the bottom K
* https://leetcode.com/problems/kth-largest-element-in-an-array
* https://leetcode.com/problems/k-closest-points-to-origin/
* https://leetcode.com/problems/minimum-cost-to-connect-sticks/
* https://leetcode.com/problems/top-k-frequent-elements/
* https://leetcode.com/problems/sort-characters-by-frequency/
* https://leetcode.com/problems/kth-largest-element-in-a-stream/
* https://leetcode.com/problems/find-k-closest-elements/
* https://leetcode.com/problems/least-number-of-unique-integers-after-k-removals/ closest leetcode or https://www.geeksforgeeks.org/maximum-distinct-elements-removing-k-elements/ for exact
* https://www.geeksforgeeks.org/sum-elements-k1th-k2th-smallest-elements/ no leetcode equivalent found
* https://leetcode.com/problems/reorganize-string/
* https://leetcode.com/problems/rearrange-string-k-distance-apart/
* https://leetcode.com/problems/task-scheduler/
* https://leetcode.com/problems/maximum-frequency-stack/

## Pattern: K-way merge
* https://leetcode.com/problems/merge-k-sorted-lists/
* Same as previous, but return the Kth smallest number
* https://leetcode.com/problems/kth-smallest-element-in-a-sorted-matrix/
* https://leetcode.com/problems/smallest-range-covering-elements-from-k-lists/
* https://leetcode.com/problems/find-k-pairs-with-smallest-sums/ small difference, grokking has different sort order and wants the largest

## Pattern: 0/1 Knapsack
* https://www.educative.io/courses/grokking-dynamic-programming-patterns-for-coding-interviews/RM1BDv71V60
* https://www.educative.io/courses/grokking-dynamic-programming-patterns-for-coding-interviews/3jEPRo5PDvx or https://leetcode.com/problems/partition-equal-subset-sum/
* https://www.educative.io/courses/grokking-dynamic-programming-patterns-for-coding-interviews/3j64vRY6JnR
* https://leetcode.com/problems/last-stone-weight-ii/ similar concept, but problem description is more abstract.
* https://leetcode.com/problems/combination-sum-ii/ similar, but return the number of combinations instead of the combinations
* https://leetcode.com/problems/target-sum/
* BONUS : Not in grokking, but I still found this very useful https://leetcode.com/problems/ones-and-zeroes/

## Pattern: Topological Sort
* First problem is identical to the following three
* https://leetcode.com/problems/course-schedule/
* https://leetcode.com/problems/course-schedule-ii/ 
* Same as above, but return all instead of any
* https://leetcode.com/problems/alien-dictionary/
* https://leetcode.com/problems/sequence-reconstruction/description/
* https://leetcode.com/problems/minimum-height-trees/

## Misc
* https://leetcode.com/problems/kth-largest-element-in-an-array/
