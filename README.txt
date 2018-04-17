Apply four patches in order.
patch -p1 < 0001-Apply-5-multipathing-patches-from-Trond.patch
patch -p1 < 0002-Enable-mNFS-for-NFSv3.patch
patch -p1 < 0003-Implement-atomic-shared-XID.patch
patch -p1 < 0004-Implement-load-balanced-distribution-of-RPCs.patch

There may be some conflicts which generates .rej files.
Those are easy to fix, and then enjoy our mNFS!
