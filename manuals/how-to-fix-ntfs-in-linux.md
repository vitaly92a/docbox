# How to fix Read-Only NTFS in OS Linux

This is solution of Read-Only NTFS problem in OS Linux.

To make external file storage not only readable but also writable, you need to do two things..

1. First, look at how your device (disk) is labeled in the file system:`sudo fdisk -l`

2. To solve the problem you can use the utility **`ntfsfix`**.

> Note: But first make sure that your device (disk) is not connected to the system. If not, run the command:

```bash
sudo umount /dev/[your_device]
```

где `your_device` - mark of your device (disk) {sdaN, sdbN, sbcN и.т.д.}

3. Excecute: 

```bash
sudo ntfsfix /dev/[your_device]
```

**Done!**
