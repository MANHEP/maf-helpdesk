# Noether Batch Compute Cluster

## What is Noether?

[Noether](https://jwa.org/encyclopedia/article/noether-emmy) is a Linux compute cluster being made available to members of the HEP Group for exploratory high-throughput computation.

The cluster presently consists of a login node, which can be accessed from the internet, job-scheduling nodes, which are private to the cluster, and a number of work-nodes, which are available to end-users via the login node under the aegis the [HTCondor](https://htcondor.com) batch schduler.
The cluster runs the [HTCondor](https://htcondor.com) batch scheduler.


## Getting an Account and First Login

To get an account on Noether please send an email to the [BLACKETT-SUPPORT](mailto:BLACKETT-SUPPORT@listserv.manchester.ac.uk) mailing list stating your lab affiliation. You will then be supplied out-of-band with an initial set of login credentials. The username assigned will be the same as your existing HEP username, if you have one; the password will be quasi-random.

Then to connect to Noether for the first time please ```ssh``` with your supplied username to ```noether.hep.manchester.ac.uk```. Please note that if you are connecting from off-Campus you will need to install an initialise the [GlobalProtect VPN](https://www.itservices.manchester.ac.uk/ourservices/popular/vpn/) tool provided by IT Services. On your initial connection attempt the supplied password will need to be changed, as in the following example:


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

Next time you ```ssh``` in you will get a shell session on the Noether login node:


```
    $ ssh mrtest@noether.hep.manchester.ac.uk
    mrtest@noether.hep.manchester.ac.uk's password: ************
    [mrtest@vm119 ~]$                       # <---- On Noether!
```

Note that the login node of Noether is presently ```vm117``` -- this may change from time to time.

## Using the Cluster.

Some brief notes and sample sessions -- this section will be amplified in due course.
### Batch jobs

We are accumulating a catalogue of sample jobs and submission scripts to be placed on GitHub. For now, if you are unfamiliar with HTCondor batch job submission, please refer to [this guide](https://htcondor.readthedocs.io/en/latest/users-manual/quick-start-guide.html).

### Interactive Sessions

Noether also supports interactive shell sessions on work-nodes. Use of the login node for heavy computational work is *prohibited*: users are expected to conduct their interactive shell sessions on certain work-nodes that have been set aside for that purpose. It is also *prohibited* to directly ```ssh``` to any work-node: users should issue the command ```condor_submit -i getenv=True``` as in the following example:

```
    $ condor_submit -i  getenv=True
    1 job(s) submitted to cluster 2724.
    Welcome to slot1_1@wn3801320.hep.manchester.ac.uk!
    You will be logged out after 7200 seconds of inactivity.
    [mrtest@wn3801320 dir_394806]$ pwd
    /scratch/condor_pool/condor/dir_394806
```
Here the shell session of user ```mrtest``` was teleported to work-node ```wn3801320``` *under the auspices of the HTCondor scheduler* (hence the time limit). Note that the working directory ```getenv=True``` is *not* ```mrtest```'s home directory on Noether! -- it is a *scratch directory* which is *local to the node*. Heavy IO work should be *confined to these local scratch directories*.  However, ```mrtest``` can easily access his *cluster-wide home directory* simply by issuing ```cd```as follows:

```
    [mrtest@wn3801320 dir_394806]$ cd
    [mrtest@wn3801320 ~]$ pwd       
    /gluster/home/mrtest                            # Now in cluster-wide $HOME directory
    [mrtest@wn3801320 ~]$ cd $_CONDOR_SCRATCH_DIR
    [mrtest@wn3801320 dir_394806]$ pwd 
    /scratch/condor_pool/condor/dir_394806          # Now back in job-specific node-local scratch directory
```

It is thus necessary to *copy critical code and data back into one's home or Lab directory* before the interactive session terminates.

