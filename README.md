# ------------------------------
# Linear Search - Static Input
# ------------------------------

def linearSearch(array, n, x):
    for i in range(0, n):
        if array[i] == x:
            return i
    return -1

array = [2, 4, 0, 1, 9, 3, 7, 8, 6, 5]
x = 7
n = len(array)
result = linearSearch(array, n, x)
if result == -1:
    print("Element not found")
else:
    print("Element found at index:", result)


# ------------------------------
# Linear Search - User Input
# ------------------------------

def search(arr, N, x):
    for i in range(0, N):
        if arr[i] == x:
            return i
    return -1

arr = []
n = int(input("Enter the size of array: "))
for i in range(n):
    a = int(input(f"Enter element {i + 1}: "))
    arr.append(a)
print("The array is: \n", arr)
x = int(input("Enter the element to be found: "))
N = len(arr)
result = search(arr, N, x)
if result == -1:
    print("Element is not present in array")
else:
    print("Element is present at position", result)


# ------------------------------
# Binary Search - Static Input
# ------------------------------

def binary_search(list1, n):
    low = 0
    high = len(list1) - 1
    mid = 0

    while low <= high:
        mid = (high + low) // 2
        if list1[mid] < n:
            low = mid + 1
        elif list1[mid] > n:
            high = mid - 1
        else:
            return mid
    return -1

list1 = [12, 24, 32, 39, 45, 50, 54]
n = 45
result = binary_search(list1, n)
if result != -1:
    print("Element is present at index", str(result))
else:
    print("Element is not present in list1")


# ------------------------------
# Binary Search - User Input
# ------------------------------

def bin_search(arr, x):
    low = 0
    high = len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] < x:
            low = mid + 1
        elif arr[mid] > x:
            high = mid - 1
        else:
            return mid
    return -1

arr = []
n = int(input("Enter the size of the array: "))
for i in range(n):
    a = int(input(f"Enter element {i + 1}: "))
    arr.append(a)

arr.sort()
print("The sorted array is: \n", arr)

x = int(input("Enter the element to be found: "))
result = bin_search(arr, x)

if result != -1:
    print("Element is present at position", result)
else:
    print("Element is not present in the array")


# ------------------------------
# Bubble Sort
# ------------------------------

def bubbleSort(arr):
    n = len(arr)
    for i in range(n - 1):
        swapped = False
        for j in range(n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        if not swapped:
            break

n = int(input("Enter the number of elements: "))
arr = []
for i in range(n):
    element = int(input(f"Enter element {i + 1}: "))
    arr.append(element)
print("\nThe array is: ")
for k in range(len(arr)):
    print(arr[k], end=" ")
bubbleSort(arr)
print("\n\nSorted array:")
for j in range(len(arr)):
    print(arr[j], end=" ")


# ------------------------------
# Selection Sort
# ------------------------------

n = int(input("Enter the number of elements: "))
arr = []
for i in range(n):
    v = int(input(f"Enter element {i + 1}: "))
    arr.append(v)
print("\nThe array is: ")
for k in range(len(arr)):
    print(arr[k], end=" ")
for i in range(len(arr) - 1):
    min_idx = i
    for j in range(i + 1, len(arr)):
        if arr[min_idx] > arr[j]:
            min_idx = j
    arr[i], arr[min_idx] = arr[min_idx], arr[i]
print("\n\nSorted array:")
for j in range(len(arr)):
    print(arr[j], end=" ")


# ------------------------------
# Insertion Sort
# ------------------------------

def insertionSort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key

n = int(input("Enter the number of elements: "))
arr = []
for i in range(n):
    v = int(input(f"Enter element {i + 1}: "))
    arr.append(v)
print("\nThe array is: ")
for k in range(len(arr)):
    print(arr[k], end=" ")
insertionSort(arr)
print("\n\nSorted array:")
for j in range(len(arr)):
    print(arr[j], end=" ")


# ------------------------------
# Stack Operations
# ------------------------------

def push(stack, item, max_size):
    if len(stack) < max_size:
        stack.append(item)
        print(f"Pushed item is: {item}")
    else:
        print("Stack overflow: cannot push item")

def pop(stack):
    if stack:
        item = stack.pop()
        print(f"Popped item is: {item}")
    else:
        print("Stack underflow cannot pop item")

def display_stack(stack):
    print("Current Stack:", stack)

def main_stack():
    stack = []
    max_size = int(input("Enter the maximum size of the stack: "))

    while True:
        print("\nStack Operations:")
        print("1. Push")
        print("2. Pop")
        print("3. Display Stack")
        print("4. Exit")
        choice = input("Enter your choice (1-4): ")

        if choice == '1':
            item = input("Enter the item to push: ")
            push(stack, item, max_size)

        elif choice == '2':
            pop(stack)

        elif choice == '3':
            display_stack(stack)

        elif choice == '4':
            print("Exiting the program")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 4.")

if __name__ == "__main__":
    main_stack()


# ------------------------------
# Queue Operations
# ------------------------------

def enqueue(queue, item, max_size):
    if len(queue) < max_size:
        queue.append(item)
        print(f"Enqueued item is: {item}")
    else:
        print("Queue overflow: cannot enqueue item")

def dequeue(queue):
    if queue:
        item = queue.pop(0)
        print(f"Dequeued item: {item}")
    else:
        print("Queue Underflow - Cannot dequeue item")

def display_queue(queue):
    print("Current queue:", queue)

def main_queue():
    queue = []
    max_size = int(input("Enter the maximum size of the queue: "))

    while True:
        print("\nQueue Operations:")
        print("1. Enqueue")
        print("2. Dequeue")
        print("3. Display queue")
        print("4. Exit")
        choice = input("Enter your choice (1-4): ")

        if choice == '1':
            item = input("Enter the item to enqueue: ")
            enqueue(queue, item, max_size)

        elif choice == '2':
            dequeue(queue)

        elif choice == '3':
            display_queue(queue)

        elif choice == '4':
            print("Exiting the program")
            break
        else:
            print("Invalid choice. Please enter a number between 1 and 4.")

if __name__ == "__main__":
    main_queue()


# ------------------------------
# Min-Heap (Priority Queue) Operations
# ------------------------------

def heapify_up(heap, i):
    while i > 0:
        parent = (i - 1) // 2
        if heap[i] < heap[parent]:
            heap[i], heap[parent] = heap[parent], heap[i]
            i = parent
        else:
            break

def heapify_down(heap, n, i):
    smallest = i
    left = 2 * i + 1
    right = 2 * i + 2
    
    if left < n and heap[left] < heap[smallest]:
        smallest = left
    
    if right < n and heap[right] < heap[smallest]:
        smallest = right
    
    if smallest != i:
        heap[i], heap[smallest] = heap[smallest], heap[i]
        heapify_down(heap, n, smallest)

def enqueue(heap, value):
    heap.append(value)
    heapify_up(heap, len(heap) - 1)

def dequeue(heap):
    if not heap:
        return None
    n = len(heap)
    min_value = heap[0]
    heap[0] = heap[n -
