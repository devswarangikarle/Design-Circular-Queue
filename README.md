# Design-Circular-Queue

Design your implementation of the circular queue. The circular queue is a linear data structure in which the operations are performed based on FIFO (First In First Out) principle, and the last position is connected back to the first position to make a circle. It is also called "Ring Buffer".
One of the benefits of the circular queue is that we can make use of the spaces in front of the queue. In a normal queue, once the queue becomes full, we cannot insert the next element even if there is a space in front of the queue. But using the circular queue, we can use the space to store new values.
Implement the MyCircularQueue class:

MyCircularQueue(k) Initializes the object with the size of the queue to be k.
int Front() Gets the front item from the queue. If the queue is empty, return -1.
int Rear() Gets the last item from the queue. If the queue is empty, return -1.
boolean enQueue(int value) Inserts an element into the circular queue. Return true if the operation is successful.
boolean deQueue() Deletes an element from the circular queue. Return true if the operation is successful.
boolean isEmpty() Checks whether the circular queue is empty or not.
boolean isFull() Checks whether the circular queue is full or not.
You must solve the problem without using the built-in queue data structure in your programming language. 

class MyCircularQueue:

    def __init__(self, k: int):
        self.size = k
        self.arr = []

    def enQueue(self, value: int) -> bool:
        if len(self.arr) == self.size:
            return False
        self.arr.append(value)
        return True

    def deQueue(self) -> bool:
        if len(self.arr) == 0:
            return False
        self.arr.pop(0)
        return True

    def Front(self) -> int:
        if self.arr:
            return self.arr[0]
        return -1

    def Rear(self) -> int:
        if self.arr:
            return self.arr[-1]
        return -1

    def isEmpty(self) -> bool:
        return not self.arr

    def isFull(self) -> bool:
        return len(self.arr) == self.size

