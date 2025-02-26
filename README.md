# useful_commands

- Checking current nvidia driver installed

```bash
cat /proc/driver/nvidia/version
```

- Checking cuda version

```bash
nvcc -V
```
- check fedora version

```bash
cat /etc/fedora-release
cat /etc/*-release
```

- check firmware type of your system (`BIOS` or `UEFI`)
```bash
[ -d /sys/firmware/efi ] && echo UEFI || echo BIOS
```
- List available disks
```bash
lsblk -f -p
```

- see current kernel version

```bash
uname -r
# or
uname -mrs
```

- see available kernels
```bash
rpm -qa kernel  # fedora
```

- conda remove packages and tarballs

```bash
# first check what it is deleting
conda clean --all --dry-run -v
# or
conda clean --tarballs --dry-run -v

#then
conda clean --all
```

- conda remove an environment
```bash
# to remove an environment completely
conda remove -n envname --all
```

- removing pip packages

```python
# to see pip cache
python -m pip cache info

# to clear pip cache
python -m pip cache purge
```

- check ssh login history
- https://askubuntu.com/questions/387664/is-there-a-way-to-check-if-others-are-logged-into-server-when-you-are
- https://unix.stackexchange.com/questions/123029/history-of-ip-addresses-that-accessed-a-server-via-ssh
```bash
journalctl -r /usr/sbin/sshd

# To see login history for users you can use last -i. This will show all logins and IP addresses since start of current logfile /var/log/wtmp
last -i | sort -r | uniq -w 20

who -u

zgrep sshd /var/log/auth.log* | grep rhost | sed -re 's/.*rhost=([^ ]+).*/\1/' | sort -u
```

- Check available repos (fedora)
```bash
grep -E "^\[.*]" /etc/yum.repos.d/*
```

- full paths of the files and directories in the current directory
```bash
find "$PWD"
```

