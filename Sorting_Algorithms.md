Bubble sort is a simple and straightforward sorting algorithm that repeatedly steps through the list to be sorted, compares adjacent elements, and swaps them if they are in the wrong order. The process is repeated until the list is sorted. It gets its name because smaller elements "bubble" to the top of the list.

### How Bubble Sort Works

1. **Initial Pass**:
   - Compare the first two elements.
   - If the first element is greater than the second, swap them.
   - Move to the next pair of elements and repeat the process until the end of the list.

2. **Subsequent Passes**:
   - After the first pass, the largest element is in its correct position at the end of the list.
   - Repeat the process for the remaining elements, excluding the last sorted element.
   - Each pass moves the next largest element to its correct position.
   - The algorithm continues until no more swaps are needed.

### Example

Let's sort the array `[5, 1, 4, 2, 8]` using bubble sort:

**First Pass**:
- Compare 5 and 1 → swap → `[1, 5, 4, 2, 8]`
- Compare 5 and 4 → swap → `[1, 4, 5, 2, 8]`
- Compare 5 and 2 → swap → `[1, 4, 2, 5, 8]`
- Compare 5 and 8 → no swap → `[1, 4, 2, 5, 8]`

**Second Pass**:
- Compare 1 and 4 → no swap → `[1, 4, 2, 5, 8]`
- Compare 4 and 2 → swap → `[1, 2, 4, 5, 8]`
- Compare 4 and 5 → no swap → `[1, 2, 4, 5, 8]`
- Compare 5 and 8 → no swap → `[1, 2, 4, 5, 8]`

**Third Pass**:
- Compare 1 and 2 → no swap → `[1, 2, 4, 5, 8]`
- Compare 2 and 4 → no swap → `[1, 2, 4, 5, 8]`
- Compare 4 and 5 → no swap → `[1, 2, 4, 5, 8]`
- Compare 5 and 8 → no swap → `[1, 2, 4, 5, 8]`

The array is now sorted. The algorithm stops as no swaps are needed.

### Bubble Sort Implementation in Python

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        # Track whether any swaps were made in this pass
        swapped = False
        for j in range(0, n - i - 1):
            # Compare adjacent elements
            if arr[j] > arr[j + 1]:
                # Swap if they are in the wrong order
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        # If no swaps were made, the array is already sorted
        if not swapped:
            break
    return arr

# Example usage
arr = [5, 1, 4, 2, 8]
sorted_arr = bubble_sort(arr)
print("Sorted array:", sorted_arr)
```

### Key Points
- **Time Complexity**: O(n^2) in the worst and average cases. This makes bubble sort inefficient on large lists.
- **Space Complexity**: O(1) because it is an in-place sorting algorithm.
- **Stability**: Bubble sort is a stable sorting algorithm since it does not change the relative order of elements with equal keys.
- **Best Use Case**: Bubble sort is primarily used for educational purposes and is not suitable for large datasets. It might be used for small datasets or nearly sorted data where its performance can be acceptable.
