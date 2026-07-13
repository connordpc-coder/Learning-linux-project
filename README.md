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
- bash= active shell session
- top= system mionitoring tool- cpu / memory usage
- htop= easier to read top

---

### VM clock sync troubleshooting
During my originalsetup of the Ubuntu VM and runnuing some basic scripts, i noticed vm's clock was not synchronising correctly.
looked into the issue to filtered and diagnos the issue

![VM clock sync troublwshooting](screenshots/sync%20problem.png)

#### Goal
To get the Vm's clock working correctly, so i can update/upgrade the machine

#### Ivestigation
- i first used journalctl | grep -i time to see what was installed under time 
- then verified the state of the clock with timedatectl status
- aftrer that i then turned off the NTP server with sudo timedatectl set-ntp false then used timedatectl again to make sure its definately turned off
- then switched it back on sudo timedatectl set-ntp true which booted the ntp server back up to the correct date

 #### problem

 after the investigation, i used timedatectl and realised that the clock still wasn't synced which initailly lead me to worry.
 
 #### resolution
However, it was just a realisation on my part that when flipping the ntp server on and off that the time service might take a minute or two before reaching the NTP server and confirming that the clock is synced and when using timedatectl the clock synchronisation status showed as "yes"
 
 
 #### What i learned
- how to troubleshoot time sync issues using timedatectl
- the difference between an active NTP server and a synchronised clock
- why linux server depend on time accuracy
- eventually this problem came up again making the ntp on and off an almost temporary solution and the permanent solution was the way i logged out the VM using save state rather than sudo shutdown now

 ![VM clock sync troublwshooting](screenshots/grep%20sync.png)
  
 
 
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


- daemon = background service that runs continously without user interaction
- systemctl status = view serivice status
-  ...ctl restart =  restart a service
-  ...ctl stop = stop a service
-  ...ctl start = start a service
-  ...ctl is enabled= checks if service is active

- example practiced with: systemctl ... chronyd following syncing issues with the vm

---

 ### loggimg

 used to check movement in services similar to transactional movements on sap 

 - history= inputs logged in session
 - journalctl= displays systems logs/journal
 - ... -xe = recent logs in more detail
 - ... -u ssh = logs for ssh service
 - ... -b = logs since last boot
 - ... -p warning= shows warnings, error and critcal log messages
 -  -p = priority

 -  used jornalctl to understand how to navigate back through logs
 -  filtered logs by service when ;ooking at ssh logs(-u ssh)
 -  used systemctl to turn off ssh, view the logs then turn it back on and view again
 -  view warnings using journalctl -p warning
 -  learned ow to categories log messages by most important
  
   ---

   ### Networking

- resolver=translates domain names into ip
- ARP=ip to find MAc
- hostname= host machine
- 127.0.0.1= loopback/ local host
- ping google
- ping 8.8.8.8
- curl= to transfer /download data from servers
- ipconfig.me= website that returns your public address
- ip a= network interface and ip address
- ss tuln= linux netstat equivelent shows listening ports
- port 22= default network port used by ssh
- ip route= routing table / default gateway
- cat/etc/resolv.conf= shows dns resolver configurations
- systemctl status ssh = checks ssh status
- sudo systemctl stop/ start ssh= stops /starts ssh
- sudo .... enable/disable ssh= shuts off or gets ssh back up and running
- ssh localhost= tests if your local host is working
- ssh-keygen= generates authentication keys
- ip neigh= shows neighbouring devices 
- reachable= device confirmed actice
- stale = device known but inactive
- failed = device unreachable

 ---

### automation
---
