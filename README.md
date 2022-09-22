# SPFS

TBD

### Getting Started

##### Building SPFS

```CONFIG_FS_DAX ``` is required to build SPFS. The recommended configurations are as follows.

```
CONFIG_SPFS=m
CONFIG_SPFS_BLOCK_BITS=8
# CONFIG_SPFS_UNIFIED_PCL is not set
# CONFIG_SPFS_DEBUG is not set
CONFIG_SPFS_READDIR_RADIX_TREE=y
# CONFIG_SPFS_STATS is not set
# CONFIG_SPFS_1SEC_PROFILER is not set
# CONFIG_SPFS_BW_PROFILER is not set
```

##### Using SPFS

1. Mounting disk file systems

   ```# mount -t ext4 /dev/sda /mnt```

2. Mounting SPFS in two operation modes

   * Standalone mode

     ```# mount -t spfs -o pmem=/dev/pmem0,format,mode=pm /mnt /mnt```

   * Stacked mode

     ```# mount -t spfs -o pmem=/dev/pmem0,format /mnt /mnt```

## Limitation

* SPFS is under development, and only some functions have been implemented and tested.
* Currently, mount-time format option(```format``` mount option) is required for every mount attempt because ```CONFIG_SPFS_READDIR_RADIX_TREE``` is under development.
