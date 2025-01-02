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


### Selection Sort

**Selection sort** is a simple comparison-based sorting algorithm. It works by dividing the input list into two parts: a sorted sublist of items which is built up from left to right and a sublist of the remaining unsorted items.

#### How Selection Sort Works

1. **Initial Pass**:
   - Find the smallest (or largest, depending on sorting order) element in the unsorted sublist.
   - Swap this element with the leftmost unsorted element, moving the boundary between the sorted and unsorted sublists.

2. **Subsequent Passes**:
   - Move the boundary one element to the right.
   - Repeat the process until the whole list is sorted.

#### Example

Let's sort the array `[64, 25, 12, 22, 11]` using selection sort:

**First Pass**:
- Find the minimum (11) and swap with the first element → `[11, 25, 12, 22, 64]`

**Second Pass**:
- Find the minimum (12) and swap with the second element → `[11, 12, 25, 22, 64]`

**Third Pass**:
- Find the minimum (22) and swap with the third element → `[11, 12, 22, 25, 64]`

**Fourth Pass**:
- Find the minimum (25) and swap with the fourth element → `[11, 12, 22, 25, 64]`

The array is now sorted.

#### Selection Sort Implementation in Python

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        # Find the minimum element in the remaining unsorted array
        min_idx = i
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        # Swap the found minimum element with the first unsorted element
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr

# Example usage
arr = [64, 25, 12, 22, 11]
sorted_arr = selection_sort(arr)
print("Sorted array:", sorted_arr)
```

#### Key Points
- **Time Complexity**: O(n^2) in all cases.
- **Space Complexity**: O(1) because it is an in-place sorting algorithm.
- **Stability**: Selection sort is not a stable sorting algorithm.

---

### Insertion Sort

**Insertion sort** is a simple sorting algorithm that builds the final sorted array one item at a time. It is much less efficient on large lists than more advanced algorithms such as quicksort, heapsort, or merge sort.

#### How Insertion Sort Works

1. **Initial Pass**:
   - Take the second element and compare it with the first element, swapping if necessary.

2. **Subsequent Passes**:
   - Take the next element and compare it with the elements in the sorted sublist.
   - Insert it into the correct position to keep the sublist sorted.
   - Repeat until the entire list is sorted.

#### Example

Let's sort the array `[12, 11, 13, 5, 6]` using insertion sort:

**First Pass**:
- Consider the second element (11) and insert it into its correct position → `[11, 12, 13, 5, 6]`

**Second Pass**:
- Consider the third element (13) and insert it into its correct position → `[11, 12, 13, 5, 6]`

**Third Pass**:
- Consider the fourth element (5) and insert it into its correct position → `[5, 11, 12, 13, 6]`

**Fourth Pass**:
- Consider the fifth element (6) and insert it into its correct position → `[5, 6, 11, 12, 13]`

The array is now sorted.

#### Insertion Sort Implementation in Python

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr

# Example usage
arr = [12, 11, 13, 5, 6]
sorted_arr = insertion_sort(arr)
print("Sorted array:", sorted_arr)
```

#### Key Points
- **Time Complexity**: O(n^2) in the worst and average cases. O(n) in the best case (when the array is already sorted).
- **Space Complexity**: O(1) because it is an in-place sorting algorithm.
- **Stability**: Insertion sort is a stable sorting algorithm.

---

### Merge Sort

**Merge sort** is an efficient, stable, comparison-based, divide-and-conquer sorting algorithm. Most implementations produce a stable sort, meaning that the order of equal elements is preserved.

#### How Merge Sort Works

1. **Divide**:
   - Split the array into two halves.

2. **Conquer**:
   - Recursively sort each half.

3. **Combine**:
   - Merge the two sorted halves to produce the sorted whole.

#### Example

Let's sort the array `[38, 27, 43, 3, 9, 82, 10]` using merge sort:

**Divide**:
- Split into `[38, 27, 43]` and `[3, 9, 82, 10]`

**Conquer**:
- Split `[38, 27, 43]` into `[38]` and `[27, 43]`
- Split `[27, 43]` into `[27]` and `[43]`
- Split `[3, 9, 82, 10]` into `[3, 9]` and `[82, 10]`
- Split `[3, 9]` into `[3]` and `[9]`
- Split `[82, 10]` into `[82]` and `[10]`

**Combine**:
- Merge `[27]` and `[43]` into `[27, 43]`
- Merge `[38]` and `[27, 43]` into `[27, 38, 43]`
- Merge `[3]` and `[9]` into `[3, 9]`
- Merge `[82]` and `[10]` into `[10, 82]`
- Merge `[3, 9]` and `[10, 82]` into `[3, 9, 10, 82]`
- Merge `[27, 38, 43]` and `[3, 9, 10, 82]` into `[3, 9, 10, 27, 38, 43, 82]`

The array is now sorted.

#### Merge Sort Implementation in Python

```python
# time running n log n
def merge_sort(arr):
    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2
    left_half = merge_sort(arr[:mid])
    right_half = merge_sort(arr[mid:])

    return merge(left_half, right_half)

def merge(left, right):
    result = []
    while left and right:
        if left[0] <= right[0]:
            result.append(left.pop(0))
        else:
            result.append(right.pop(0))

    while left:
        result.append(left.pop(0))

    while right:
        result.append(right.pop(0))

    return result

# Example usage:
arr = [38, 27, 43, 3, 9, 82, 10]
sorted_arr = merge_sort(arr)
print("Sorted array:", sorted_arr)


# Example usage
arr = [38, 27, 43, 3, 9, 82, 10]
sorted_arr = merge_sort(arr)
print("Sorted array:", sorted_arr)
```

#### Key Points
- **Time Complexity**: O(n log n) in all cases.
- **Space Complexity**: O(n) due to the additional space required for the temporary arrays.
- **Stability**: Merge sort is a stable sorting algorithm.

---

### Quick Sort

**Quick sort** is an efficient, comparison-based, divide-and-conquer sorting algorithm. It works by selecting a 'pivot' element from the array and partitioning the other elements into two sub-arrays, according to whether they are less than or greater than the pivot.

#### How Quick Sort Works

1. **Partition**:
   - Select a pivot element from the array.
   - Rearrange the array so that all elements with values less than the pivot come before it, and all elements with values greater come after it.

2. **Recursively Sort**:
   - Recursively apply the above steps to the sub-arrays of elements with smaller and larger values.

#### Example

Let's sort the array `[10, 7, 8, 9, 1, 5]` using quick sort:

**Initial Pass**:
- Choose a pivot (let's say 5).
- Partition the array around the pivot → `[1, 5, 8, 9, 10, 7]`.

**Subsequent Passes**:
- Recursively apply quick sort to the sub-arrays `[1]` and `[8, 9, 10, 7]`.
- Choose a pivot (let's say 7) for the right sub-array and partition → `[1, 5, 7, 9, 10, 8]`.
- Recursively apply quick sort to the sub-arrays `[9, 10, 8]`.
- Choose a pivot (let's say 8) and partition → `[1, 5, 7, 8, 10, 9]`.
- Recursively apply quick sort to the sub-array `[10, 9]`.
- Choose a pivot (let's say 9) and partition → `[1, 5, 7, 8, 9, 10]`.

The array is now sorted.

#### Quick Sort Implementation in Python

```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    else:
        pivot = arr[len(arr) // 2]
        left = [x for x in arr if x < pivot]
        middle = [x for x in arr if x == pivot]
        right = [x for x in arr if x > pivot]
        return quick_sort(left) + middle + quick_sort(right)

# Example usage
arr = [10, 7, 8, 9, 1, 5]
sorted_arr = quick_sort(arr)
print("Sorted array:", sorted_arr)
```

#### Key Points

- **Time Complexity**: 
  - Average case: O(n log n)
  - Worst case: O(n^2) (This happens when the pivot selection is poor, such as when the smallest or largest element is always chosen as the pivot)
  
- **Space Complexity**: O(log n) due to the recursion stack in the average case. However, it can be O(n) in the worst case.

- **Stability**: Quick sort is not a stable sorting algorithm. Equal elements may not retain their original relative positions after sorting.

#### Optimizations and Variants

1. **Choosing a Good Pivot**:
   - Randomly selecting a pivot can help ensure a good average-case performance.
   - Median-of-three method: choose the median of the first, middle, and last elements as the pivot.

2. **Tail Call Optimization**:
   - Recur into the smaller sub-array first and use a loop for the larger sub-array to optimize the space complexity.

3. **Insertion Sort for Small Arrays**:
   - For very small arrays, quick sort's overhead is higher than that of simple algorithms like insertion sort. Hybrid algorithms use quick sort for large arrays and switch to insertion sort for small arrays.


