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
- Each directory node contains linked lists of files and subdirectories.
## Functionalities
### 1. File Management Module
- Create a new file (touch filename).
- Delete a file (rm filename).
- Rename a file (mv oldname newname).
- Open and write content to a file (open filename, write filename).
- Read a file's content (read filename).
- Display file metadata (size, type, creation date).
### 2. Directory Management Module
- Create a new directory (mkdir dirname).
- Delete a directory (recursively remove all contents) (rmdir dirname).
- Navigate to a directory (cd dirname).
- List contents of the current directory (ls).
- Display current path (pwd).
### 3. Search & Navigation Module
- Search for a file in the system (find filename).
- Display current directory path (pwd).
- Traverse the directory tree to list all files (tree).
## Code Outline
### 1. Defining Structures
```cpp
struct File {
 string name;
 string content;
 int size;
 File* next;
};

struct Directory {

 string name;

 vector<File*> files;

 vector<Directory*> subDirs;

 Directory* parent;

};

```

### 2. Creating a Directory

```cpp

void mkdir(string dirName) {

 Directory* newDir = new Directory{dirName, {}, {}, currentDir};

 currentDir->subDirs.push_back(newDir);

 cout << "Directory '" << dirName << "' created.\n";

}

```

### 3. Navigating Between Directories

```cpp

void cd(string dirName) {

 if (dirName == ".." && currentDir->parent != nullptr) {

 currentDir = currentDir->parent;

 return;

 }

 for (auto dir : currentDir->subDirs) {

 if (dir->name == dirName) {

 currentDir = dir;

 return;

 }

 }

 cout << "Directory not found!\n";
}
```

