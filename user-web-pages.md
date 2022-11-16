# User web pages

Some users of the particle physics interactive cluster are able to publish web pages and other 
files on users.hep.manchester.ac.uk However for most people, the University's 
[personal pages service](https://personalpages.manchester.ac.uk/personalwebpages.html) or a 
lab service like 
[CERN's AFS websites](https://espace.cern.ch/webservices-help/websitemanagement/ConfiguringAFSSites/Pages/PermissionsforyourAFSfolder.aspx)
will be better options.

To publish files on the particle physics users webserver, place the files in the WWW subdirectory 
of your home directory on AFS. If your AFS username is EXAMPLE, then your personal website 
appears at https://users.hep.manchester.ac.uk/u/EXAMPLE/ . You can create subdirectories 
within your WWW directory which appear as further subdirectories under /u/EXAMPLE/ on 
the web. 

To make a web page, the file needs to be in HTML format with file extension .html 

If a file index.html exists in a directory, then that page is displayed to viewers when
they view web URLs ending in slash. For example, ~/WWW/test1/index.html will be displayed
when viewers go to https://users.hep.manchester.ac.uk/u/EXAMPLE/test/ 

If no index.html file exists, then a directory listing of all files in that directory and 
the names of any subdirectories is shown. This is a convenient way to publish sets of 
documents, but can allow welcome visitors to browse around and find things you don't want 
them to see.

The AFS directories should be readable by the AFS www:webservers group. This can be checked
by going into the directory and executing the command fs listacl which should dislay a list 
of permissions including   www:webservers rl

It is not possible to enable users websites to run CGI scripts, PHP pages, and other forms of
dynamic content. 
