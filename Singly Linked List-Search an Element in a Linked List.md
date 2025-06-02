# # 🔍 Singly Linked List-To Search an Element in a Linked List

This project contains a simple implementation of a **singly linked list** in Python, allowing insertion and searching of elements.

---

## 🎯 Aim

To write a Python program to search for a given element in a singly linked list using object-oriented programming principles.

---

## 🧠 Algorithm

1. **Define a Node class** with `data` and `next` attributes.
2. **Define a LinkedList class** with:
   - A `head` pointer initialized to `None`.
   - A `push()` method to add elements at the beginning.
   - A `search()` method to check whether a given value exists.
3. Create a `LinkedList` instance.
4. Insert the elements **10, 30, 11, 21, 14** using `push()` (which results in reverse order).
5. Read an integer input from the user.
6. Use `search()` to check if the element exists in the list.
7. Output **"Yes"** if found, else **"No"**.

---

## 💻 Program
      class Node:
          def __init__(self, data):
              self.data = data
              self.next = None
      
      class LinkedList:
          def __init__(self):
              self.head = None
          
          def push(self, data):
              new_node = Node(data)
              new_node.next = self.head
              self.head = new_node
          
          def search(self, key):
              current = self.head
              while current:
                  if current.data == key:
                      return True
                  current = current.next
              return False
      
      # Create linked list and insert elements
      llist = LinkedList()
      for value in [10, 30, 11, 21, 14]:
          llist.push(value)
      
      # Read input from user
      key = int(input())
      
      # Search and output result
      if llist.search(key):
          print("Yes")
      else:
          print("No")
## Sample Output
![image](https://github.com/user-attachments/assets/f9eb31ae-9a9c-4734-994d-955d8687d9c1)

## Result
The program creates a linked list by pushing elements in reverse order. The list ends up as: 14 -> 21 -> 11 -> 30 -> 10. It then reads a number from the user and searches through the list. If the number exists, it prints "Yes", otherwise "No". For the input 21, since it exists in the list, the output is "Yes".
