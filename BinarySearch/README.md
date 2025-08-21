# Binary Search (Python)

## What is Binary Search?
Binary Search is a searching algorithm used to search for an element or condition in **sorted data**. It works by repeatedly halving the search space. Time complexity: `O(log n)`.

## Algorithm
```
# Find an index where `nums[i] == target`, or return -1 if not found.

def binary_search(nums, target):
    left, right = 0, len(nums) - 1         # 2 pointers setting to top left and top right of the input array  
    while left <= right:                   
        mid = (left + right) // 2          # Another space saving formula: mid = left + (right - left // 2)
        if nums[mid] < target:             # If mid is smaller than targer, discard the left half and make left pointer (mid + 1)
            left = mid + 1
        elif nums[mid] > target:           # If mid is larger than targer, discard the right half and make right pointer (mid - 1)
            right = mid - 1
        else:
            return mid                     # mid = target
    return -1

```

## Example Usage
```
nums = [-5, -2, 0, 1, 5, 9]
target = 5
index = binary_search(nums, target)
print(index)  # Output: 4 (index of 5)
```

### References
https://www.youtube.com/watch?v=9nmrkG6QtpQ 
