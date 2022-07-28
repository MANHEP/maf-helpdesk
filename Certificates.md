# How to get certificates
x509 certificates in the UK are provided by the [UK e-Science CA](https://portal.ca.grid-support.ac.uk/). There are different tools but for users the easiest is to go through the WEB portal. Ignore the other methods.

The proccess of requesting a certificate is a pre-requisite to register to a VO (Virtual Organisation) and is a **separate** procedure usually carried out by different set of administrators particularly for what concerns large VOs such as the LHC experiments. Occasionally, in Manchester the people are the same because we manage the GridPP VOMS which supports a number of smaller groups. 
# New Certificates
New certificates have an approval procedure which must be followed to demonstrate the person requesting the certificate is who they say they are and are part of the University of Manchester.
There are two procedures one in person and, since covid, one virtual one.
## In person
The [basic procedure in person](https://ca.grid-support.ac.uk/#the-basic-process) requires that you bring an ID document and possibly your university card. The ID document needs to be scanned so if you have a scanned copy you can preventively send it to the operator that will check it matches. The operator also has to verify the PIN you used during the certificate request. 
## Virtual (on zoom)
The [virtual procedure](https://ca.grid-support.ac.uk/#uk-escience-certification-authority) requires that you show the the same documents and the same scans but on top of this you will also need to show that you can connect to the [UK Federation service](https://wayf.ukfederation.org.uk/DS-20160527/uk.ds?entityID=https%3A%2F%2Ftest.ukfederation.org.uk%2Fentity&return=https%3A%2F%2Ftest.ukfederation.org.uk%2FShibboleth.sso%2FUKfedDS%3FSAMLDS%3D1%26target%3Dcookie%253A1647417064_9284) using your university credentials. This has to happen **during** the video call **not** before. 
# Renewals
If you used to have a certificate but you let it expire it is possible that the RA might ask you to go through the same procedure above again. Do not let it expire!

For a normal renewal while your certificate is still valid instead only the PIN is required and it can all be handled automatically.
# Managing certificates
Once the procedure is completed you'll receive an email telling you can download the certificate. After this you will have a copy in your browser which needs to be exported and converted from a single P12 file format to a two files public and private PEM keys that you can use with grid tools. All the commands and explanations you need are on this [useful page](https://ca.grid-support.ac.uk/certificatemanagement/)
# CERN certificates
People on LTA may require a CERN certificate. The procedure is completely different and you can find the information on the [CERN CA site](https://ca.cern.ch/ca/) Manchester RAs are not responsible for CERN certificates.