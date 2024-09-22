
# #100DaysOfCode Challenge - Progress Tracker

Welcome to my journey of the #100DaysOfCode challenge! This repository will serve as a log of my daily progress. Each day I'll document what I learn, build, and improve as I work through various coding challenges and projects.

## Day 1: [Linked Lists in Python](#day-1-linked-lists-in-python)

**Date:** 22/09/2024

### What I Learned:
- Implemented a **Doubly Linked List** in Python.
- Created methods to:
  - Insert at the start, end, and at a specific position.
  - Remove elements from any position.
  - Handle edge cases such as empty lists and out-of-bounds indices.
  - Display the linked list in a clean, readable format.

### Key Code Snippet:
```python
class Node:
    def __init__(self, data=None, next=None, prev=None):
        self.data = data
        self.next = next
        self.prev = prev


class DoublyLinkedList:
    def __init__(self):
        self.head = None
        self.tail = None

    def insert_at_end(self, data):
        if self.head is None:
            node = Node(data, self.head, self.tail)
            self.head = node
            self.tail = node
            return

        node = Node(data, None, self.tail)
        self.tail.next = node
        self.tail = node

    def insert_at_start(self, data):
        if self.head is None:
            node = Node(data, self.head, self.tail)
            self.head = node
            self.tail = node
            return
        node = Node(data, self.head, None)
        self.head.prev = node
        self.head = node

    def insert_values(self, data_list):
        for data in data_list:
            self.insert_at_end(data)

    def get_length(self):
        count = 0
        itr = self.head
        while itr:
            count += 1
            itr = itr.next
        return count

    def remove_at(self, index):
        if index < 1 or index > self.get_length():
            print("Out of Index")
            return

        if self.get_length() == 1 and index == 1:
            self.head = None
            self.tail = None
            return

        if index == 1:
            self.head = self.head.next
            if self.head:
                self.head.prev = None
            return
        if index == self.get_length():
            self.tail = self.tail.prev
            if self.tail:
                self.tail.next = None
            return

        itr = self.head
        count = 1
        while itr:
            if count == index:
                itr.prev.next = itr.next
                itr.next.prev = itr.prev
                return
            itr = itr.next
            count += 1

    def insert_at(self, index, data):
        if index < 1 or index > self.get_length() + 1:
            print("Out of Index")
            return

        if index == 1:
            self.insert_at_start(data)
            return

        if index == self.get_length() + 1:
            self.insert_at_end(data)
            return

        itr = self.head
        count = 1
        while itr:
            if count == index:
                node = Node(data, itr, itr.prev)
                itr.prev.next = node
                itr.prev = node
                return
            count += 1
            itr = itr.next

    def display(self):
        if self.head is None:
            print("Linked List is Empty")
            return
        string = ""
        itr = self.head
        while itr:
            string += str(itr.data)
            if itr.next:
                string += "-->"
            itr = itr.next
        print(string)



ll = DoublyLinkedList()
ll.insert_at_end(1)
ll.insert_at_end(2)
ll.insert_at_start(0)
ll.insert_values([3, 4, 5])
ll.display()
ll.insert_at(2, 10)
ll.remove_at(3)
ll.remove_at(5)
ll.display()

```

### Reflections:
- Understanding how linked lists work in memory.
- Improved my approach to handling edge cases.
- Optimized my code structure for clarity and efficiency.

### Next Steps:
- Continue learning advanced linked list operations.
- Explore other data structures like stacks and queues.

---



## Overall Goals:
- Enhance understanding of data structures & algorithms.
- Build new projects, tackle coding challenges.
- Sharpen problem-solving and debugging skills.

---

### Follow My Progress:
- Connect with me on Twitter: [balaganesh_003](https://x.com/balaganesh_003)
- Let's code together!

