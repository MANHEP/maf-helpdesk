# Noether Compute Cluster: Basic Usage #

### What is Noether? ###

Noether is a Linux compute cluster being made available to members of the HEP Group for exploratory high-throughput computation.

The cluster presently consists of a login node, which can be accessed from the internet, job-scheduling nodes, which are restricted to the sysadmins, and a number of work-nodes, which are available to end-users via the login node *only* under the aegis the [HTCondor](https://htcondor.com) batch schduler.

### Getting an Account and First Login ###

As expained in the [FAQ](https://github.com/MANHEP/maf-helpdesk/blob/master/noether_faq.md), to request an account on Noether, please ask your supervisor/line manager to send an email to the [BLACKETT-SUPPORT](mailto:BLACKETT-SUPPORT@listserv.manchester.ac.uk) mailing list. When your request is approved, you will be supplied out-of-band with an initial set of login credentials.

Then to connect to Noether for the first time please ```ssh``` with your supplied username to ```noether.hep.manchester.ac.uk```. Please note that if you are connecting from off-Campus you will need to install an initialise the [GlobalProtect VPN](https://www.itservices.manchester.ac.uk/ourservices/popular/vpn/) tool provided by IT Services. On your *initial connection attempt the supplied password will need to be changed*, as in the following sample `ssh` session:
```
    $ ssh mrtest@noether.hep.manchester.ac.uk
    Password: *******                                            # <---- enter the issued password
    WARNING: Your password has expired.
    You must change your password now and login again!
    Changing password for user mrtest.
    Current Password: *******                                    # <---- enter the issued password AGAIN
    New password: ************                                   # <---- now choose a NEW password
    Retype new password: ************                            # <---- re-enter your NEW password
    passwd: all authentication tokens updated successfu lly.
    Connection to noether.hep.manchester.ac.uk closed.
```
The next time you `ssh` to Noether, entering the new password will give you a shell session on the Noether:
```
    $ ssh mrtest@noether.hep.manchester.ac.uk
    mrtest@noether.hep.manchester.ac.uk's password: ************
    [mrtest@vm119 ~]$                                            # <---- On Noether's login node!
```

### Interactive Sessions ###

Use of the login node for heavy computational work is *prohibited*: users are expected to conduct intensive interactive shell sessions the clusters work-nodes, some of which have been set aside for this purpose. Now *directly ssh-ing to a work-node is not permitted*: users should issue the command `condor_submit -i` or the alias `qrsh`  as in the following example:

```
    $ condor_submit -i  getenv=True
    1 job(s) submitted to cluster 2724.
    Welcome to slot1_1@wn3801320.hep.manchester.ac.uk!
    You will be logged out after 7200 seconds of inactivity.
    [mrtest@wn3801320 dir_394806]$ pwd
    /scratch/condor_pool/condor/dir_394806
```
Here the shell session of user `mrtest` was teleported to work-node ```wn3801320``` *under the auspices of the HTCondor scheduler* (hence the time limit). Note that the working directory `getenv=True` is *not* `mrtest`'s home directory on Noether! -- it is a *scratch directory* which is *local to the node*. Heavy IO work should be *confined to these local scratch directories*.  However, ```mrtest``` can easily access his *cluster-wide home directory* simply by issuing ```cd```as follows:

```
    [mrtest@wn3801320 dir_394806]$ cd
    [mrtest@wn3801320 ~]$ pwd       
    /gluster/home/mrtest                            # Now in cluster-wide $HOME directory
    [mrtest@wn3801320 ~]$ cd $_CONDOR_SCRATCH_DIR
    [mrtest@wn3801320 dir_394806]$ pwd 
    /scratch/condor_pool/condor/dir_394806          # Now back in job-specific node-local scratch directory
```

It is thus necessary to *copy critical code and data back into one's home or Lab directory* before the interactive session terminates.


