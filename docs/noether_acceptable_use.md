# Noether Compute Cluster: Acceptable Use #

### Preamble ###

This document has been written to provide end-users of the
**Noether Compute Cluster** (hereafter the *cluster*,
**Noether** or the *equipment*) with directions as to
acceptable use of the equipment. In the first instance it is addressed
to *staff and postgraduate students* in the HEP Group of the Department
of Physics and Astronomy (hereafter the *group*) at the University of
Manchester, but it is expected that all and any persons who are, or may
become, affiliated with the group and who wish to use
**Noether** shall have recourse to it before access is granted. It is not
intended to be a technical description of, or instruction manual for
**Noether**: please see the [FAQ](https://manhep.github.io/maf-helpdesk/noether_faq/) for the the latter.

### Terminology ###

We deem a the actions of an end-user of **Noether** to be
*unacceptable* if it they are *in potential breach of United Kingdom
law*, the University's general *regulations and statutes*, the rules set
forth in the document *Acceptable Use Policy - IT Facilities and
Services* or if they *fail to accord with the instructions herein
mandated*. We deem usage to be *inappropriate* when it fails to be
*professional, collegial or courteous* by academic workplace standards,
or when it generally does not accord with such guidelines as may be set
forth in the present document.

### Breaches ###

Any breach of *acceptable* use is liable to incur *summary
termination* of the offending user's batch jobs and shell sessions on
**Noether** and *temporary suspension* of that user's account.
Thesis supervisors, affiliated PIs and the Head of Group may be
consulted in confidence when this action is initiated. Access will be
restored as and when all parties are satisfied that no intentional
repeat of the breach will occur. We shall deal leniently with
*inappropriate* use, unless it becomes habitual, in which case again,
the academic superiors of the culpable party are liable to be consulted.

### Requesting an Account ###

Accounts on Noether are in the first instance available to postgraduates
and staff in the group, but subject to consideration, academic
collaborators on Campus or beyond may also be eligible. Postgraduates
requesting an account *must be sponsored by their Supervisor or PI*.
Accounts are requested by sending an email to the
[BLACKETT-SUPPORT](mailto:blackett-support@listserv.manchester.ac.uk) mailing list. Requests will usually be
actioned within one working day of receipt. There is no charge for an
account.

### Home Directories ###

Users are granted a *home directory* with a small initial selection of
'dotfiles' and sample HTCondor scripts: this directory
are subject to a *quota* as specified in the [FAQ](https://manhep.github.io/maf-helpdesk/noether_faq/
); if you require additional capacity, you must request it via [BLACKETT-SUPPORT](mailto:blackett-support@listserv.manchester.ac.uk).

### Expiry of Accounts ###

Accounts are by default suspended when their owner's leaving date (as
recorded by Campus HR) is attained. Of course dispensations to keep
accounts active beyond this point may be countenanced subject to the
approval of the Head of Group. After six months from the date of
suspension, all files and data on **Noether** directly owned
by the account, including the home directory, are liable to be made
unavailable, and the account itself deactivated.

### Group Membership ###

Your **Noether** account will receive a POSIX
group id corresponding to to your primary *experimental
affiliation* and you will have access to *a corresponding data area*.
You may not source or copy data from any other experimental data
location without permission: if you have obtained that permission please
forward the evidence in an email to [BLACKETT-SUPPORT](mailto:blackett-support@listserv.manchester.ac.uk) and
we will adjust your account accordingly.

### Connecting to Noether ###

Only account-holders are permitted to connect to **Noether**
connections shall be to the *designated login node* only and *an ssh
client must be used*. It is permissible for users to authenticate to the
cluster by means of ssh-key, provided that key is protected by a non-trivial
(strong) passphrase.

### The Batch System ###

All end-users of *Noether* are expected to employ the
cluster's HTCondor batch scheduler: all *intensive and non-trivial*
computational tasks, including long compilations, *must be submitted* to
it, whereupon they will be allocated to a work-node. It is *absolutely
prohibited* to subvert the batch system by logging directly on to
work-nodes: users must run interactive sessions (other than their login
shell) under the aegis of HTCondor; a small number of
work-nodes have been set aside for this purpose.

### Obtaining Support ###

If the answer to your support request is not
contained in the [FAQ](https://manhep.github.io/maf-helpdesk/noether_faq/) then please send an email to [BLACKETT-SUPPORT](mailto:blackett-support@listserv.manchester.ac.uk)
This mailing list is read by the cluster's systems administrators: they should respond to
queries within one working day.

### Conclusion ###

These regulations have been approved by the Head of Group and IT Team,
Particle Physics in the University of Manchester. Should additions or
amendments transpire from time to time, they will be announced in the
[BLACKETT-SUPPORT](mailto:blackett-support@listserv.manchester.ac.uk) mailing list, and this document will be
updated accordingly, the current version being posted at the [present location](https://manhep.github.io/maf-helpdesk/noether_acceptable_use/).
