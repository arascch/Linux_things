## Find a suspicious files

>[!note]
>combine find and locate and permissions

find a file:
- owner isn't root
- have 777 permission
- be in /var dir
```
#sudo find /var -type f -perm 0777 ! -user root
```

find a file with incomplete name in /etc dir and save to a file

```
#locate -i conf* > suspicious_files.log
```

Enjoy it ;)

