# Merge Sort (Python)

## What is Merge Sort?

Merge Sort is a **divide-and-conquer** algorithm that:
- Divides the array into halves recursively
- Sorts each half (Since at the end of each half recursion, one one item is left and 1 item is sorted itself)
- Merges the sorted halves (for each item from both arrays, puts the smaller one first)

Its time complexity is `O(n log n)` for all cases (best/worst/average).

## Merge Sort Algorithm

```
def merge_sort(arr):
    if len(arr) <= 1:
        return arr                            # returns the single item

    mid = len(arr) // 2
    left = merge_sort(arr[:mid])              # recurse left and right halves
    right = merge_sort(arr[mid:])

    return merge(left, right)                 # return merged left and right


def merge(left, right):
    merged = []
    i = j = 0

    while i < len(left) and j < len(right):   # Until either of the arrays ends
        if left[i] <= right[j]:
            merged.append(left[i])
            i += 1
        else:
            merged.append(right[j])
            j += 1

    merged.extend(left[i:])                   # add any leftover items (Since they are already sorted)
    merged.extend(right[j:])
    return merged
```
