mdwiki
======

Wiki written using markdown

# Chroot da Arch a Debian
Rricordarsi di montare i filesystem necessari:

```sh
MY_CHROOT=/debian
mount proc $MY_CHROOT/proc -t proc
mount sysfs $MY_CHROOT/sys -t sysfs
mount -o bind /dev/ $MY_CHROOT/dev/
chroot $MY_CHROOT /bin/bash
export PATH=/bin:/sbin:/usr/bin:/usr/sbin:${PATH}
```

Poi ricordarsi di smontare tutto:

```sh
sync; sync; sync
umount $MY_CHROOT/proc $MY_CHROOT/sys $MY_CHROOT/dev/
umount $MY_CHROOT
```
