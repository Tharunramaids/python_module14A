# Queue Implementation in Python

## Aim
To implement a circular queue using a class in Python and demonstrate basic enqueue and dequeue operations following the FIFO (First In First Out) principle.

## Procedure
1. Define a `Queue` class with a fixed-size list to hold elements.
2. Initialize the queue with attributes:
   - `items`: List of fixed size
   - `head`: Points to the front of the queue
   - `tail`: Points to the rear of the queue
   - `size`: Current number of elements
3. `enqueue(item)`:
   - Adds an element to the queue at the `tail` position.
   - Updates the `tail` and `size`.
   - Checks if the queue is full before adding.
4. `dequeue()`:
   - Removes an element from the `head` of the queue.
   - Updates the `head` and `size`.
5. `is_list_full()`:
   - Checks if the queue has reached its maximum size.
6. `is_empty()`:
   - Checks if the queue is empty.
7. Accept size and 3 elements from the user and enqueue them.
8. Print the queue’s current state.

## Program

```python
# Queue simply works in FIFO
class Queue:
    def __init__(self, size):
        self.items = [0] * size
        self.max_size = size
        self.head, self.tail, self.size = 0, 0, 0

    def enqueue(self, item):
        if self.is_list_full():
            print('Queue is full')
            return
        self.items[self.tail] = item
        self.tail = (self.tail + 1) % self.max_size
        self.size += 1

    def dequeue(self):
        item = self.items[self.head]
        self.head = (self.head + 1) % self.max_size
        self.size -= 1
        return item

    def is_list_full(self):
        return self.size == self.max_size

    def is_empty(self):
        return self.size == 0

# User input
size = int(input())
queue = Queue(size)

str = float(input())
str1 = float(input())
str2 = float(input())

queue.enqueue(str)
queue.enqueue(str1)
queue.enqueue(str2)

# Output the internal state of the queue
print(queue.items)
```

## output
![Screenshot 2025-04-20 213136](https://github.com/user-attachments/assets/4b75f6e3-e375-4668-8c13-c0804f1cf45b)

## result
The program successfully demonstrates the working of a circular queue. It enqueues user-input values and prints the internal state of the queue.
