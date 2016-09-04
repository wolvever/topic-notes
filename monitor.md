
## Check status

* Get kernel version `uname -r`
* Get cpu core count `cat /proc/cpuinfo | grep processor | wc -l`
* Get load of (1min, 5min, 15min)  `uptime`, `top`
* Get disk usage `du -h`
* Get disk, mount point, usage `df -h`
* Get disk read throughput `hdparm -t /dev/sda2`
* Get disk bufferred read throughput `hdparm -T /dev/sda2`
* Get disk write throughput `dd if=/dev/zero of=/root/testfile bs=1G count=1 oflag=direct`
* Get disk write lantency `dd if=/dev/zero of=/root/testfile bs=512 count=1000 oflag=direct`

