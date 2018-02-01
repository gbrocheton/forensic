# forensic

### Export disk image

[...]

### Check start sector & sector size with fdisk

```bash
$ fdisk -l disk.raw
[...]
Sector size (logical/physical): 512 bytes / 512 bytes
[...]
Device    Boot  Start End       Sectors   Size  Id  Type
disk.raw1 *     2048  31457279  31457279  15G   83  Linux
```

### Mount disk file system with an offset equal to start-sector*sector-size

```bash
$ sudo mount -o ro,loop,offset=1048576 disk.raw /mnt/diskfs
```

