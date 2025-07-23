## Simple user Creation

combine the commands for create user, group, and permission in ubuntu 24.04

### create a user and join to projteam group
```
#useradd -m -G projteam sara
#useradd -m -G projteam ali
#useradd -m -G projteam mina
```

### create directory for this group and change the owner to root user and group to projteam

```
#mkdir /srv/projteam
#chown root:projteam /srv/
#chown root:projteam projteam/

```

###change the permissions only for users to change and write thing into this folder
```
#chmod  770 projteam
#chmod -R 670 srv/
```

Enjoy it.
