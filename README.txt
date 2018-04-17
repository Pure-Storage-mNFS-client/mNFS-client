Apply four patches in order.
patch -p1 < 0001-Apply-5-multipathing-patches-from-Trond.patch
patch -p1 < 0002-Enable-mNFS-for-NFSv3.patch
patch -p1 < 0003-Implement-atomic-shared-XID.patch
patch -p1 < 0004-Implement-load-balanced-distribution-of-RPCs.patch

The first patch is from Trond Myklebust Linux NFS client maintainer.
See reference: https://www.spinics.net/lists/linux-nfs/msg63368.html
The last three patch allow multipathing in NFSv3 and improve performance with load balancing.

There may be some conflicts which generates .rej files.
Those are easy to fix, and then enjoy our mNFS!
