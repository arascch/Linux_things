## Create User In Ubuntu
in this part, try to create to two user with diffrent privilage. one of them is admin user (without privilage to reboot and shutdown system) and\ another is a normal user and create a user profile for them.

> create a normal user:
```
\\normal user
#sudo useradd -m -G users arashaskari
#sudo passwd arashaskari

```

> create sudo user:

```
\\sudo user
#sudo useradd -m arashask
#sudo passwd arashask
sudo usermod -aG sudo arashask
```

> Restrict new sudo user\

>[!NOTE]
> for restriction we have 2 method , one of them is a create seprate file for new user and then set the access or user visudo file directly.

```
\\\firstly create a file for our user in /etc/sudoers.d/arashask

#sudo visudo -f /etc/sudoers.d/testadmin
```

> into the file:
```
arashask ALL=(ALL) ALL
Cmnd_Alias SHUTDOWN_CMDS = /sbin/shutdown, /sbin/reboot, /bin/systemctl reboot, /bin/systemctl poweroff, /sbin/halt, /sbin/poweroff
arashask ALL = ALL, !SHUTDOWN_CMDS
```

## delete normal user but home directory don't change
```
sudo userdel arashaskari
```

>[!TIP]
> if you use `-r` flag , This user's home directory will also be deleted.

## Disable access to `SSH` with Root user

> edit the `sshd_config` file

> /etc/ssh/sshd_config

```
PermitRootLogin no

```

> into teminal:
```
sudo systemctl restart sshd
```

## force user to change password in first login

```
sudo user -m arash
sudo passwd arash
sudo chage -d 0 arash
```

## export commands from history

```
history > /home/arashask/history.txt
```

`Have a Good Moment`
