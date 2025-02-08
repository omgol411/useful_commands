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
```

- see kernel version

```bash
uname -r
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
