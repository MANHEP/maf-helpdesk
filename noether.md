### Noether Batch Compute Cluster

The Noether batch compute cluster is available to members of the HEP Group for exploratory batch and interactive high-throughput computation.

The cluster presently consists of a login node and seven work-nodes. The current work-nodes have the following specification:

16 cores, 64 GB main memory, 850 GB fast local stoage
    
Home directories and per-lab data areas are available on two shared network volumes, each having a total initial capacity of 15TB.

The cluster runs the [HTCondor](https://htcondor.com) batch scheduler. The system is presently in beta testing: if it proves useful it will be expanded.

To get an account on Noether please send an email to the [BLACKETT-SUPPORT](mailto:BLACKETT-SUPPORT@listserv.manchester.ac.uk) mailing list stating your lab affiliation.

You will be provided with an initial set of credentials out-of-band. The username assigned will be the same as your existing HEP username (if any).

The password will need to be changed on your initial login as in the following example:

```
$ ssh mrtest@noether.hep.manchester.ac.uk
WARNING: Your password has expired.
You must change your password now and login again!
Changing password for user mrtest.
Current Password: *******               # <---- enter your supplier password
New password: ************              # <---- now choose a secure password
Retype new password: ************       # <---- re-enter your secure password
passwd: all authentication tokens updated successfully.
Connection to noether.hep.manchester.ac.uk closed.
```

Then to access the cluster you must ssh in again:
```
ssh mrtest@noether.hep.manchester.ac.uk
mrtest@noether.hep.manchester.ac.uk's password: ************
[mrtest@vm119 ~]$                       # <---- NB the login node's local name is vm117 -- this may change.
```


