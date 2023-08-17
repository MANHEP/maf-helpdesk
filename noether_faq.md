# Noether Compute Cluster: Frequently Asked Questions #

### Section A. General ###

A1. **What is Noether?**

Noether is the HEP Group's 'Tier3' end-user research computation cluster, consisting of several loosely-coupled physical and virtual machines. Shared home directory and data areas are mounted from a [Gluster](https://www.gluster.org/) farm, and by using the [HTCondor|https://htcondor.org/] scheduler, users can run batch or interactive sessions on the cluster.

A2. **How do I request an account on Noether?**

Please send an email to [BLACKETT-SUPPORT] cc-ing an academic sponsor and indicating which experimental data your account will be allowed to access. We aim to action such requests within 24h.

A3. **How many work-nodes does Noether have and what are their memory and CPU specifications?**

There are presently 24 work-nodes: 8 having 96 cores / 384GB RAM (4GB/core Intel(R) Xeon(R) Gold 5220R CPU @ 2.20GHz) and the remaining 12 work-nodes having 16 cores / 64 GB RAM (4GB/core Intel(R) Xeon(R) CPU E5-2620 v4 @ 2.10GHz). The total is therefore currently 864 cores, though in practice this may vary somewhat as equipment is added, retired or placed under maintenance.

### Section B. Storage ###

B1. **What storage is available on Noether and what is its visibility?**

Globally visible data and home directory areas are available with a total capacity of 0.25 PB. Each work-node has a much smaller (and volatile) local 'scratch' area of around 7TB: you should only use 'scratch' as a staging area for ongoing batch work: all code and data you wish to retain on Noether must be copied to your home directory or shared data area.

B2. **Where should I place 'big data' on Noether?**

We have organised per-experiment data diretories on Noether, mounted under `/gluster/data`; all large datasets should be placed here for optimal access in computations. Your initial access to this area will correspond to your experimental affiliation. Access to additional areas will be granted upon request subjecxt to stakeholder approval.

B3. **What are the quotas for the Home and Data areas on Noether?**

All end-user home directories, which are to be found under `/gluster/home`, are assigned an initial capacity of 5GB, whereas the per-experiment data directories are assigned 10TB. This large datasets should not be kept in one's home directory. If you run over capacity you will be unable to create new files. You must either free up space or request in increase to your quota via the [BLACKETT-SUPPORT] list.

B4. **Are the Home and Data areas backed up?**

*No they are not backed up* presently: it is therefore essential that users of Noether ensure that *all critical code and data* are regularly `rsync`-ed (or otherwise transferred) to a secure and resilient out-of-band location, such as an encrypted external hard-drive.


### Section C. Usage ###

C1. **How do I connect to Noether?**

You must use an ssh-client to connect to Noether. if you use Linux or Mac OS then you may simply `ssh <your_username>@noether.hep.manchester.ac.uk` The proceedure for resetting your initially assigned password is given in the email sent to you when your account is created. If you use Windows then it it recommended either to use PuTTy or the Windows Subsystem for Linux.

C2. **What is a typical workflow on Noether?**

Most users will wish to 'start small' in their home directory under an interactive htcondor session on one of the work-nodes. When code is running correctly, it is then matter of writing a shell-script and htcondor submission file to automate matters. In this way you may scale up your workflow, conduct parameterised 'sweeps' and so on.

C3. **How do I start an interactive session on a work-node?**

In brief, one issues `condor_submit -i` or simply `qrsh` to be 'teleported' to a work-node of Noether (a subset of work-nodes has been set aside for interactive sessions). More details are given in [here](noether_basic_usage.md)

C4. **How do I submit a batch job into the HTCondor scheduler queue?**

A simple example of the use of HTCondor to run batch jobs is given [ibid](noether_basic_usage.md)

### Section D. Resource Limits ###

D1. **How do I request such and such a CPU or memory resource for the job I submit?**

D2. **How do I submit multiple parameterized copies of the same task into the queue?**

D3. **What is the maximum number of jobs I may have running on work-nodes?**

### Section E. Miscellany ###

E1. **What software applications are available on Noether.**

Not many at the moment: just standard Linux system utilities and what can be found by delving into [CVMFS](https://cvmfs.readthedocs.io/en/stable/) which is mounted cluster-wide.

E2. **I already have an account on the machines `pc2012, pc2013, pc1014, higgs` and the shared GPU machines. Can I use the same home directory on Noether?**

Unfortunately we cannot use the 'old-style' AFS home directories on Noether, but we can certainly assist with copying data across to the new infrastructure, subject to quota.

E3. **Max Noether or Emmy Noether?**

[Emmy](https://jwa.org/encyclopedia/article/noether-emmy).
