# queue_py

````py

----queue using list
 
 Using list: 
q  = []
q.append(10)
q.append(20)
q.append(30)
print(q)

q.pop(0)
q.pop(0)
print(q)


 
 ---------queue using deque: 

Using deque: 
from collections import deque

q = deque()

q.append('a')
q.append('b')
q.append('c')
print(q)

q.popleft()
q.popleft()
print(q)

-------queue using array without pointer
class queue: 
    def __init__(self, size): 
        self.q = []
        self.size  = size

    def enqueue(self, element):
        if len(self.q) == self.size: 
            print('queue is full')  
        else: 
            self.q.append(element)
    def dequeue(self):
        if not self.q: 
            print('queue is empty')
        else: 
            e = self.q.pop(0)
            print('element removed', e)

    def display(self): 
        print(self.q)
        while True: 
            print('select 1. Add 2. delete 3. display 4. quit')
            choice = int(input())
            if choice  == 1:  
                self.enqueue(int(input()))
            elif choice == 2: 
                self.dequeue()
            elif choice == 3: 
                self.display()
            elif choice == 4: 
                break
            else: 
                print("invalid input")

d = queue(3)
d.display()

 
 -----Queueu using array with front and rear pointer
 
 Array based: 
class Array_Queue: 
    def __init__(self, c): 
        self.queue = []
        self.front = self.rear = 0
        self.capacity  = c

    def queueEnqueue(self, data): 
        if self.capacity == self.rear: 
            print("Queue is full")
        else: 
            self.queue.append(data)
            self.rear += 1

    def queueDequeue(self):
          if self.front == self.rear: 
              print("queue is empty")
          else: 
              x = self.queue.pop(0)
              print('\ndeleted data', x)
              self.rear  -= 1
            
    def queueDisplay(self):
          if self.front == self.rear: 
              print("Queue is empty")
          for i in self.queue: 
              print(i, "<--", end='')
    def queueFront(self):
          if self.front == self.rear: 
              print('queue is empty')

          print("Front elements is: ", self.queue[self.front])

q  = Array_Queue(4)

q.queueDisplay()
q.queueEnqueue(20)
q.queueEnqueue(40)
q.queueEnqueue(60)

q.queueDisplay()
q.queueDequeue()
q.queueDisplay()

----------------circular queue implementation--

class circularQueue: 
    def __init__(self, size):
        self.size  = size
        # initialized with None for all the values for size
        self.queue = [None for i in range(size)]
        # must be -1 as 0 is a valid data and sized array
        self.front = self.rear = -1 

    def enqueue(self, data):
        if (self.rear + 1) % self.size  == self.front:
            print(' Queue is full')

        # condition for empty empty queue
        elif self.front  == -1:
            self.front = 0
            self.rear  = 0
            self.queue[self.rear] = data
        else: 
            self.rear = (self.rear + 1) % self.size
            self.queue[self.rear] = data

    def dequeue(self):

        if self.front  == -1: 
            print('Queue full')
        elif self.front == self.rear: 
            temp = self.queue[self.front]
            self.front = -1
            self.rear  = -1
            return temp
        else: 
            temp = self.queue[self.front]
            self.front = (self.front + 1) % self.size
            return temp
    def display(self): 
        if self.front == -1: 
             print("Queue is empty")
        elif self.rear >= self.front: 
             for i in range(self.front, self.rear + 1): 
                print(self.queue[i], end = " ")
                print()
        else: 
              print('Element in queue', end = " ")
              for i in range(self.front, self.size):
                  print(self.queeu[i], end = " ")
              for i in range(0, self.rear + 1):
                  print(self.queue[i], end = " ")
              print()
        if (self.rear + 1) % self.size == self.front: 
              print('Queue is full')

# driver code
ob  = circularQueue(5)
ob.enqueue(14)
ob.enqueue(22)
ob.enqueue(44)
ob.enqueue(55)
ob.enqueue(-1)
ob.display()
print('deleted value=', ob.dequeue())
ob.display()


````
