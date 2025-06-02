# 📝 Doubly Linked List: Search an Element

This Python program demonstrates the implementation of a **Doubly Linked List** where you can insert elements at both the beginning and the end of the list. Additionally, it allows you to search for a specific element in the list.

---

## 🎯 Aim

To write a Python program that:
- Implements a **Doubly Linked List** with functions to insert elements at the beginning and the end of the list.
- Implements a search function to check if a given element exists in the list.

---

## 🧠 Algorithm

1. **Step 1:** Define a class `Nodeq` with:
   - `data` to store the node's value.
   - `next` to store the reference to the next node.
   - `prev` to store the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `head` to point to the first node.

3. **Step 3:** In the `DoublyLinkedList` class, define methods:
   - `insert_beginning(data)` to insert a node at the beginning.
   - `insert_end(data)` to insert a node at the end.
   - `search(data)` to search for an element in the list.

4. **Step 4:** Create an instance of `DoublyLinkedList`.
   - Insert elements at the beginning and end.
   - Search for specific elements.

---

## 💻 Program
      class Nodeq:
          def __init__(self, data):
              self.data = data
              self.next = None
              self.prev = None
      
      class DoublyLinkedList:
          def __init__(self):
              self.head = None
      
          def insert_beginning(self, data):
              new_node = Nodeq(data)
              if self.head is None:
                  self.head = new_node
                  return
              new_node.next = self.head
              self.head.prev = new_node
              self.head = new_node
      
          def insert_end(self, data):
              new_node = Nodeq(data)
              if self.head is None:
                  self.head = new_node
                  return
              curr = self.head
              while curr.next is not None:
                  curr = curr.next
              curr.next = new_node
              new_node.prev = curr
      
          def search(self, data):
              curr = self.head
              while curr is not None:
                  if curr.data == data:
                      return True
                  curr = curr.next
              return False
      
      dll = DoublyLinkedList()
      
      dll.insert_beginning(10)
      dll.insert_beginning(20)
      dll.insert_end(30)
      dll.insert_end(40)
      
      print(dll.search(20))  # True
      print(dll.search(50))  # False

## Sample Output
![image](https://github.com/user-attachments/assets/fc0d6a4a-887a-498c-b245-445cddea110b)

## Result
The program defines a doubly linked list with nodes having data, next, and prev. It supports inserting nodes at the beginning and end of the list, and searching for elements. The search method correctly returns True if the element exists, otherwise False. The output confirms the presence of 20 and absence of 50 in the list.
