# Question 3 - File System and Link Analysis

- echo > original.txt: Created a file with sample text content.
- ls -li: Showed the inode number of original.txt (1310882), which 
  uniquely identifies its data on disk.
- ln original.txt hardlink.txt: Created a hard link. It shares the 
  exact same inode number as the original, meaning both filenames 
  point to the same underlying data blocks.
- ln -s original.txt symlink.txt: Created a symbolic link, which got 
  its own separate inode (1310884) and simply stores the path text 
  "original.txt" rather than the actual data.
- stat: Confirmed hardlink.txt has identical metadata (inode, size, 
  timestamps) to original.txt, while symlink.txt has completely 
  different metadata and is marked as a "symbolic link" file type.
- rm original.txt: Deleted the original file. Afterward, hardlink.txt 
  still worked perfectly (data was preserved because the inode had 
  another link keeping it alive), while symlink.txt broke and returned 
  "No such file or directory" since it only referenced a filename that 
  no longer existed.
- Conclusion: Hard links are resilient to deletion of the original 
  filename because they reference the same inode/data directly, while 
  symbolic links are just pointers to a path and become "dangling" or 
  broken if the target file is removed.
