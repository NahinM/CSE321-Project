CSE 321: Operating Systems SimpleFS Lab Term Project

Group Number: 14

Group Members:
1.  Student ID: 23201183 Name: Nahin Munkar
2.  Student ID: 22201287 Name: Md. Tanzimul Islam 
3.  Student ID: 23201039 Name: Priyanti Biswas

COMPILE
gcc -Wall -Wextra -std=c11 simplefs_builder.c -o simplefs_builder
gcc -Wall -Wextra -std=c11 simplefs_adder.c -o simplefs_adder

RUN
./simplefs_builder --image disk.img
./simplefs_adder --input disk.img --file test1.txt

Implementation Description 
This project implements SimpleFS, a simplified educational file system
using the C programming language.

The implementation creates and modifies a binary file-system image. The
file system contains a superblock, inode bitmap, data bitmap, inode
table, root directory, and data blocks.

The project consists of two main programs:
1.  simplefs_builder.c
    -   Creates and initializes an empty SimpleFS image.
    -   Initializes the superblock.
    -   Allocates the root inode and root directory block.
    -   Creates the “.” and “..” directory entries.
2.  simplefs_adder.c
    -   Adds regular files from the current working directory into an
        existing SimpleFS image.
    -   Finds available inodes and data blocks using first-fit
        allocation.
    -   Copies file contents into allocated data blocks.
    -   Creates inode metadata and directory entries.
    -   Updates inode and data bitmaps.

Contribution of Group Members

Member 1: Md. Tanzimul Islam (22201287)

Responsibilities: - Implemented SimpleFS image creation workflow. -
Worked on superblock initialization. - Implemented inode bitmap and data
bitmap initialization. - Created and initialized the root inode. -
Implemented root directory setup including “.” and “..” entries.

Member 2: Nahin Munkar (23201183)

Responsibilities: - Implemented the main file adding functionality. -
Worked on inode allocation. - Implemented data block allocation using
first-fit strategy. - Handled file data copying into allocated blocks. -
Created file inode metadata. - Updated directory entries and filesystem
metadata.

Member 3: Priyanti Biswas (23201039)

Responsibilities: - Worked on supporting filesystem operations. -
Implemented and verified bitmap-related operations. - Assisted with
error handling and validation. - Performed testing using different file
sizes and input cases. - Prepared README documentation and project
verification.

Known Limitations / Problems

-   SimpleFS supports only the root directory. Subdirectories are not
    implemented.
-   File deletion, file renaming, permissions, symbolic links, and
    journaling are not supported.
-   Maximum regular file size is limited to 12288 bytes.
-   The implementation depends on the fixed filesystem layout provided
    in the project specification.
-   Source files must be placed in the current working directory.
-   The system does not support mounting the filesystem as a real
    operating system filesystem.