# queue_py

````py
class Queue:
  def __init__(self, capacity):
    self.nums = []
    self.capacity = capacity
    self.n = 0

  def enqueue(self, value):
    if self.n == self.capacity:
      print("capacity exceeded, cannot enqueue")
      return
    self.nums.insert(0, value)
    self.n += 1

  def dequeue(self):
    if self.n == 0:
      print("queue is empty, cannot dequeue")
      return
    self.n -= 1
    return self.nums.pop(0) # pop from the start

# testing
que = Queue(5)

que.enqueue(22)
que.enqueue(33)
que.enqueue(34)
print(que.nums)
que.dequeue()
print(que.nums)
# que.enqueue(5)
# print(que.nums)
# que.enqueue(10)
# print(que.nums)
# que.dequeue()
# print(que.nums)
# que.enqueue(100)
# print(que.nums)
# que.enqueue(200)
# print(que.nums)
# que.dequeue()
# print(que.nums)
# que.dequeue()
# print(que.nums)
# que.dequeue()
# print(que.nums)
# que.dequeue()
# print(que.nums)


````
