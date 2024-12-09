# CS-525 Advanced Database Organization

---

# README: Advanced Database Organization Assignments Overview

This document outlines the programming assignments completed for the CS 525 Advanced Database Organization course at Illinois Institute of Technology. Each assignment progressively builds components of a custom database management system, emphasizing advanced features and optimization.

## Assignment 1: Storage Manager

### Overview
Implemented a storage manager responsible for managing blocks of data within a filesystem. This component supports basic file operations and is crucial for page management within our database system.

### Features
- **File Operations**:
  - `createPageFile()`: Creates a new page file.
  - `openPageFile()`: Opens an existing page file.
  - `closePageFile()`: Closes an open page file.
  - `destroyPageFile()`: Deletes a page file.
- **Page Operations**:
  - `readBlock()`: Reads a specified block from a file.
  - `writeBlock()`: Writes a block to a specified position in the file.
  - `appendEmptyBlock()`: Appends an empty block to the file.
  - `ensureCapacity()`: Ensures the file can accommodate a specified number of pages.

### Extra Credit Achievements
- **Enhanced Error Handling**: Robust error management to prevent and recover from potential file and page management errors.
- **Optimization Techniques**: Efficient memory management strategies to minimize overhead and maximize performance.

## Assignment 2: Buffer Manager

### Overview
Developed a buffer manager to manage a fixed number of memory pages that represent disk pages, enhancing data retrieval and storage operations.

### Features
- **Buffer Pool Management**:
  - `initBufferPool()`: Initializes a buffer pool for a specific file.
  - `shutdownBufferPool()`: Shuts down and cleans up the buffer pool.
  - `forceFlushPool()`: Forces the buffer pool to write all dirty pages back to the disk.
- **Page Replacement Strategies**:
  - FIFO (First-In-First-Out)
  - LRU (Least Recently Used)
  - (Optional) CLOCK
  - (Optional) LRU-K

### Extra Credit Achievements
- **Thread Safety**: Made buffer pool functions thread-safe.
- **Advanced Replacement Strategies**: Added CLOCK and LRU-k strategies.

## Assignment 3: Record Manager

### Overview
Introduces functionality for managing records within a database, including operations to insert, delete, update, and scan records.

### Features
- **Record Manipulation**:
  - `insertRecord()`: Inserts a new record into a table.
  - `deleteRecord()`: Deletes a record from a table.
  - `updateRecord()`: Updates an existing record.
  - `scanRecords()`: Scans records based on a specified condition.
- **Table Management**:
  - `createTable()`: Creates a new table.
  - `openTable()`: Opens an existing table.
  - `closeTable()`: Closes an open table.

### Extra Credit Achievements
- **Null Value Support**: Implemented handling for SQL-style null values.
- **Primary Key Constraints**: Enforced primary key constraints on updates and inserts.
- **Interactive Interface**: Developed a simple user interface for database operations such as table definition, tuple insertion, update, and deletion.
- **Conditional Updates Using Scans**: Extended scan functionality to support conditional updates based on expressions.
- **TIDs and Tombstones**: Introduced TIDs and tombstones for managing updates and deletions efficiently.

## Assignment 4: B+-Tree Index

### Overview
Implements a B+-tree index for efficient data retrieval, integrating with the buffer manager and, optionally, the record manager.

### Features
- **B+-Tree Operations**:
  - `createBtree()`: Creates a new B+-tree.
  - `deleteBtree()`: Deletes a B+-tree.
  - `insertKey()`: Inserts a key into the B+-tree.
  - `findKey()`: Finds a key in the B+-tree.
  - `deleteKey()`: Deletes a key from the B+-tree.

### Extra Credit Achievements
- **Integration with Record Manager**: Uses the B+-tree for key-based record retrieval.
- **Support for Multiple Data Types**: Allows the B+-tree to handle different types of keys.
- **Pointer Swizzling**: Implemented pointer swizzling for more efficient node access.
- **Support for Multiple Entries per Key**: Allowed multiple entries for a single key to support duplicate key values.

---

**Additional Notes:**
Comprehensive test cases are included for each assignment to ensure functionality and robustness. Extensive error handling and performance optimization techniques have been applied to ensure high system performance and reliability.
