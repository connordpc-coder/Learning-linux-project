# Learning Linux Project

Personal Linux learning project focused on Linux administration,
permissions, scripting, troubleshooting and automation.

---


## Planned Next Steps

- expand the enviroment into a multi machine network (P2P)
- configure SSH communication between VMs
- practice client/server networking
- explore firewall rules and network troubleshooting
- continued improvement on system monitoring and scripting


## Current Topics

- Linux commands
- File permissions
- Bash scripting
- Process and service management
- Networking basics
- Troubleshooting

---

## Current Progress

Completed:
- VM setup
- Time synchronization troubleshooting
- Basic bash scripts
- chmod permissions
- Directory structures
- system-info.sh script
- Services
- Process management

Currently learning:
- Process management
- Services
- Logging

---

## Project Structure

automation/
logs/
networking/
permissions/
scripts/
---



## Project-Notes
(screenshots will be added to my screenshot folder-ongoing)

---

### commands

- pwd= where am i?
- ls= whats here?
--- ls variants ls -l,ls -a,ls -la
- mkdir= make directory/ folder
- touch= make file 
- cat= view file/quick look
- cp= copy file /folder
- mv= move/rename file
- rm = delete file
- ps aux= identifies user activity 
- systemd= service manager- daemon
- chronyd= time sync service- daemon
- bash= asctive shell session
- top= system mionitoring tool- cpu / memory usage
- htop= easier to read top

---

### scripting

- chmod= change mode permission
- x= execute permission
- += add/modifier
- |= takes output and passes it on
- (example) chmod +x backup.sh = make this file (backup.sh) runnable

  ---
  
### permission values

- d= directory
- -= file
-  r=read=4
-  w=write=2
-  x= execute=1
-  0=do nothing
-  7=4+2+1=rwx
-  6=4+2=rw
-  5=4+1=r-x
-  chmod 700 = rwx, do nothing,do nothing
-  644=read/write
-  755=onwer has full control others can only read and execute but not edit
  ---

  ### processes and management
