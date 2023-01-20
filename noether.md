### Noether Batch Compute Cluster

# What is Noether?

[Noether](https://jwa.org/encyclopedia/article/noether-emmy) is an experimental Linux cluster being made available to members of the HEP Group for exploratory batch and interactive high-throughput computation.

The cluster presently consists of a login node, job-scheduling nodes and seven work-nodes, which are available to end users.

The current work-nodes have the following specification: 16 Intel Xeon 2.6 GHz cores, 64 GB main memory, 850 GB fast local stoage
    
Home directories and per-lab data areas are available on two shared network volumes, each having a total initial capacity of 15TB.

The cluster runs the [HTCondor](https://htcondor.com) batch scheduler. The system is presently in beta testing: if it proves useful it will be expanded.

To get an account on Noether please send an email to the [BLACKETT-SUPPORT](mailto:BLACKETT-SUPPORT@listserv.manchester.ac.uk) mailing list stating your lab affiliation.

You will be provided with an initial set of credentials out-of-band. The username assigned will be the same as your existing HEP username (if any).

To connect to the cluster please ```ssh``` to ```noether.hep.manchester.ac.uk```. The issued password will need to be changed on your initial login as in the following example:

```
$ ssh mrtest@noether.hep.manchester.ac.uk
WARNING: Your password has expired.
You must change your password now and login again!
Changing password for user mrtest.
Current Password: *******               # <---- enter the issued password
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

Using the cluster: we are accumulating sample job scripts which will be placed on GitHub in due course. For now, if you are unfamiliar with HTCondor batch job submission, please refer to [this guide](https://htcondor.readthedocs.io/en/latest/users-manual/quick-start-guide.html).

Interactive sessions on Noether. 

