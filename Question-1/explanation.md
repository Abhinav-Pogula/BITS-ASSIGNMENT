# Question 1 - Linux Environment Verification

- whoami / id / groups: Displayed the current user (codespace), their UID/GID, 
  and all group memberships. This confirms identity and access scope within 
  the container environment.
- echo $SHELL: Confirmed /bin/bash as the active shell interpreter for the session.
- pwd: Verified the current working directory as /workspaces/BITS-ASSIGNMENT.
- ls -la: Listed all files and directories (including hidden ones like .git), 
  showing the full project structure with 5 Question folders already created.
- Network check: The ping utility was not available in this container, so curl 
  was used instead to send an HTTPS request to google.com. The HTTP/2 301 
  response confirmed successful network connectivity (a redirect response 
  still proves reachability).
