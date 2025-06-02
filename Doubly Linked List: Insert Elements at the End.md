# 📚 Doubly Linked List: Insert Elements at the End of a Doubly Linked List

This Python program demonstrates the creation and manipulation of a **Doubly Linked List** where elements can be inserted at the **end** of the list. The program also provides a method to traverse the list and display the elements.

---

## 🎯 Aim

To write a Python program that:
- Implements a **Doubly Linked List**.
- Allows insertion of elements at the end of the list.
- Provides functionality to traverse the list and display its elements.

---

## 🧠 Algorithm

1. **Step 1:** Define a class `Node` to represent each node in the doubly linked list with attributes:
   - `item` for storing the data of the node.
   - `nref` for storing the reference to the next node.
   - `pref` for storing the reference to the previous node.

2. **Step 2:** Define a class `DoublyLinkedList` with:
   - `start_node` to point to the first node of the list.

3. **Step 3:** Define methods in the `DoublyLinkedList` class:
   - `insert_in_emptylist(data)` to insert an element when the list is empty.
   - `insert_at_end(data)` to insert elements at the end of the list.
   - `traverse_list()` to traverse the list and print the elements.

4. **Step 4:** Create an instance of `DoublyLinkedList` and use the `insert_at_end()` method to insert elements into the list.

5. **Step 5:** Use the `traverse_list()` method to print the elements of the list.

---

## 💻 Program
      class Node:
          def __init__(self, data):
              self.item = data
              self.nref = None
              self.pref = None
      
      class DoublyLinkedList:
          def __init__(self):
              self.start_node = None
      
          def insert_in_emptylist(self, data):
              new_node = Node(data)
              self.start_node = new_node
      
          def insert_at_end(self, data):
              if self.start_node is None:
                  self.insert_in_emptylist(data)
                  return
              n = self.start_node
              while n.nref is not None:
                  n = n.nref
              new_node = Node(data)
              n.nref = new_node
              new_node.pref = n
      
          def traverse_list(self):
              if self.start_node is None:
                  print("The list is empty")
                  return
              n = self.start_node
              while n is not None:
                  print(n.item, end=' ')
                  n = n.nref
              print()
      
      # Create doubly linked list instance
      dll = DoublyLinkedList()
      
      dll.insert_at_end(10)
      dll.insert_at_end(20)
      dll.insert_at_end(30)
      
      dll.traverse_list()

## Sample Output
![image](https://github.com/user-attachments/assets/a3763d01-69aa-4e5a-b84c-11e2ae0674d3)

## Result
The program defines a Node class for doubly linked list nodes and a DoublyLinkedList class to manage the list. It inserts elements at the end, maintaining previous and next references, and prints the elements in order when traversed. The output correctly displays the inserted elements in sequence.
