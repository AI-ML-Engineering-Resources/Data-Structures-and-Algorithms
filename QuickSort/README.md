# Quick Sort (Python)

## What is Quick Sort?

Quick Sort is a **divide-and-conquer** sorting algorithm that:
- Picks a "pivot" element
- Partitions the array so elements < pivot go left, > pivot go right
- Recursively does this until everything is sorted

**Time Complexity:** Average: `O(n log n)`, Worst: `O(n²)` 

## Quick Sort Algorithm and Implementation

```
def partition(arr, low, high):
    pivot = arr[high]                          # Pivot is the last element
    i = low

    for j in range(low, high):
        if arr[j] <= pivot:                    # If current <= pivot
            arr[i], arr[j] = arr[j], arr[i]    # swap low and current
            i += 1                             # increment low, since previous low element was swapped

    arr[i], arr[high] = arr[high], arr[i]      # swap current low and current high
    return i                                   # Return surrent low index

def quickSort(arr, low=0, high=None):
    if high is None:
        high = len(arr) - 1                    # If first call of the funtion, set high to top right
    if low >= high:
        return                                 # When low and high index are same or swaped, return to finish rest of the recursion

    p = partition(arr, low, high)              # partition index
    quickSort(arr, low, p - 1)                 # Sort 1st half before partition
    quickSort(arr, p + 1, high)                # Sort 2nd half after partition
```

## Reference
[YouTube](https://www.youtube.com/watch?v=7h1s2SojIRw )
[W3Schools](https://www.w3schools.com/dsa/dsa_algo_quicksort.php)
