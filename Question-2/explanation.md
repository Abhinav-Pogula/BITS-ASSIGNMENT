# Question 2 - Secure Project Workspace Setup

- umask: Checked the default umask (0022), which determines default 
  permissions for newly created files and directories.
- mkdir -p: Created a nested directory structure (ProjectWorkspace with 
  docs, src, logs subfolders) in a single command.
- touch: Created empty files inside each subfolder to represent project 
  documentation, source code, and logs.
- ls -l (before): Showed default permissions on readme.txt as rw-rw-rw-, 
  meaning everyone had read/write access by default in this environment.
- chmod 750/700/640: Restricted permissions differently based on file 
  sensitivity — readme.txt allows owner full access and group read/execute; 
  main.sh restricts fully to owner only since it's an executable script; 
  activity.log allows owner to write and group to read only, protecting 
  log integrity.
- ls -l (after) / stat: Confirmed permission changes were applied and 
  displayed ownership (UID/GID) and inode details for the file.
- Conclusion: Proper permission settings prevent unauthorized users from 
  reading, modifying, or executing sensitive project files, which is 
  critical for protecting project data and code integrity in a shared 
  workspace.
