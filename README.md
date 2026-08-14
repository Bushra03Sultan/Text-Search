# 🔍 Text Search and Replace System (From Scratch)
![Java](https://img.shields.io/badge/Language-Java-orange?style=for-the-badge&logo=openjdk)
![Data Structure](https://img.shields.io/badge/Data%20Structures-BST%20%2B%20Linked%20List-blue?style=for-the-badge)
![Built From Scratch](https://img.shields.io/badge/Constraints-No%20Java%20Collections-red?style=for-the-badge)
A high-performance Text Search and Replace System implemented in Java entirely from scratch, without relying on built-in collections framework classes (such as ArrayList or HashMap). 
This project combines a Custom Singly Linked List with a Binary Search Tree (BST) to achieve fast searching while maintaining sentence order and grammatical integrity.
---
## 🏗️ System Architecture & Design
Using a single data structure presents trade-offs:
* A BST automatically sorts unique words alphabetically, losing sentence structure.
* A Linked List preserves text order but requires O(m) linear time for searching.
To solve this, our design integrates two custom data structures working in tandem:

                  +--------------------------------+
                  |           input.txt            |
                  +--------------------------------+
                                  |
                   +--------------+--------------+
                   |                             |
                   v                             v
     +--------------------------+  +--------------------------+
     |   BinarySearchTree (BST) |  | CustomTextList (Linked)  |
     +--------------------------+  +--------------------------+
     | Stores UNIQUE words      |  | Preserves EXACT word     |
     | Provides O(log n) search |  | order & sentence grammar |
     +--------------------------+  +--------------------------+

1. CustomTextList (Custom Singly Linked List):
   * Appends incoming words sequentially via a tail pointer.
   * Preserves the original word order, formatting, and sentence structure.
2. BinarySearchTree (Custom BST):
   * Stores only unique words lexicographically.
   * Provides O(log n) efficient word lookup operations.
---
## 🔄 Search & Replace Workflow
When a replace operation is executed:
* Lookup: The system queries the Binary Search Tree (BST) to verify if the search word exists in O(log n) average time.
* Sequence Update: If found, it iterates through the CustomTextList to update all occurrences in the actual text.
* Tree Synchronization & Edge Case Handling:
  * The old word is deleted from the BST via node restructuring (handling leaf, single-child, or two-children node deletions).
  * If the new replacement word does not already exist in the tree, it is inserted into the BST to keep the tree accurate.
---
## 📊 Complexity Analysis

| Algorithm / Operation | Structure Used | Average Case | Worst Case | Description |
| :--- | :--- | :--- | :--- | :--- |
| Word Search | Binary Search Tree | O(log n) | O(n) | Recursive binary search traversal |
| Word Insertion | Binary Search Tree | O(log n) | O(n) | Lexicographical placement (ignores duplicates) |
| Word Deletion | Binary Search Tree | O(log n) | O(n) | Replaces node using in-order successor |
| Text Traversal & Replace | Custom Linked List | O(m) | O(m) | Sequential pass over all m words |

> Note: n represents the number of unique words in the BST, while m represents the total word count in the input text.
---
## 🖥️ Console Interface & Sample Output
```text
=====================================
1. Search for a word only
2. Replace a word
3. Display current text
4. Exit
=====================================
Choose an option (1-4): 2
Search : data
Replace with : information
Expected Output
System: Text updated successfully.
Current Text: This project applies advanced information structures to solve text processing problems. 
Status: Complete
```
---
## 🔮 Future Improvements
To prevent `O(n)` worst-case scenarios on pre-sorted text input, the tree structure can be upgraded to a **Self-Balancing Binary Search Tree** (such as an **AVL Tree** or **Red-Black Tree**). This would guarantee strict `O(log n)` search and modification bounds under all circumstances.
---
## 🚀 How to Run
1. **Clone the repository:**  
```bash
   git clone https://github.com/Bushra03Sultan/text-search-replace.git
  
2. **Navigate to project directory:**  
```bash
   cd text-search-replace
  
3. **Ensure `input.txt` is present** in the same root folder with your sample text.
4. **Compile and execute:**   
```bash
   javac TextSearchReplace.java
   java TextSearchReplace
   
---

## 👩‍💻 Author

Boshra Faruq

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Bushra03Sultan)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bushra-faruq-906696429)