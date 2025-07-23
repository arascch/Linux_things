## create system file , Mount It and permissions

assume that you added a new disk to your system and now you need mount it as a file system and use it.

- create an ext4

```
1-use fdisk for create a partition and then write partion and then close the fdisk
2- use mkfs to create ext4 partion
3- create a file e.g. /mnt/downloads/
4- mount your new partion in /etc/fstab file 
```

-find files bigger than 100MB in / directory
```
#find / max-depth=3 -type f -size +100M > /mnt/downloads/report.txt
```

enjoy it;)
