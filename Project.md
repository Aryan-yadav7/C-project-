## Idea
This project simulates a file system similar to UNIX/Linux, where users can create, delete, rename,
and navigate files and directories. 
The system will use Pointers, Structures, Linked Lists, and Trees to represent files and directories,
ensuring an efficient hierarchical storage structure.
## Application of the Project
This system will allow users to:
1. Create, Delete, and Rename Files/Folders dynamically.
2. Navigate the Directory Structure similar to UNIX/Linux (cd, ls, pwd).
3. Simulate File Storage and Hierarchy using a Tree-based Directory System.
4. Maintain File Metadata like size, creation date, and file type.
5. Perform Basic File Operations such as opening, writing, and reading a file.
## Implementation Details
### 1. Use of Structures (struct)
- File Structure: Stores details like name, size, type, and content.
- Directory Structure: Contains a list of files and subdirectories.
### 2. Use of Pointers
- Dynamic memory allocation for storing files and directories.
- Pointers to manage parent-child relationships in the directory tree.
### 3. Use of Linked List
- A linked list to maintain files inside a directory.
- A linked list to store open files to simulate file handling.
### 4. Use of Trees
- A Tree-based structure to represent directories and subdirectories.
