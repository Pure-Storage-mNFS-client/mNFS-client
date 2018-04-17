Apply four patches in order.
patch -p1 < 0001-Apply-5-multipathing-patches-from-Trond.patch
patch -p1 < 0002-Enable-mNFS-for-NFSv3.patch
patch -p1 < 0003-Implement-atomic-shared-XID.patch
patch -p1 < 0004-Implement-load-balanced-distribution-of-RPCs.patch

The first patch is from Trond Myklebust Linux NFS client maintainer.
See reference: https://www.spinics.net/lists/linux-nfs/msg63368.html
The last three patches allow multipathing in NFSv3 and improve performance with load balancing.

There may be some conflicts which generate .rej files.
But don't worry because those are easy to fix.

After rebuilding the kernel, there are two more mount options. (nconnect, xpsmode)
nconnect is the number of connections you want to open.
xpsmode=1 means original round-robin and xpsmode=2 means better load-balancing mode.
For example, 
sudo mount -v -t nfs -overs=3,nconnect=16,xpsmode=2,nolock REMOTE_FILESYSTEM LOCAL_DIRECTORY
It will open 16 connections and use load-balancing to transfer data.
