# UbuntuSwapMemory
if we use old server for MLops..., you might meet absents of memory
And it will lead your server down
In this case, increasing swap memory is the simple insurance to prevent your sever down.

check Swap file
  
- sudo free -m
- sudo swapon -s

if Swapfile exit, then stop
  
- sudo swapoff -a

Generate Swapfile

- sudo fallocate -l 8g /swapfile

change the permission for swapfile, and start swapfile works

- sduo chmod 600 /swapfile
- sudo mkswap /swapfile #ready
- sudo swapon /swapfile #active

use swapfile after reboot

- sudo vi /etc/fstab

add below contents
  
- /swapfile swap swap defaults 0 0
