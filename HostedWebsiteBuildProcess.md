# The Eternal Family Website Build Process

This website was created so that the apps used here would run on the iphone. The apps include some javascript which must be run on a server to be compatible with the iphone, hence the website. This document explains how the files are interconnected and how they work together to produce the website.

**Tools**

* /home/pi/bin/md_to_html.py
* * Converts markdown to html. It has some special options that are used by this website.

## Directories

### ~Documents/HostedWebsite

This directory contains the local files for The Eternal Family Website.

* Update index.html with any changes.
* * git status
* * Update index.html if needed.
* * * gvim index.html
* Update remote repository
* * git status
* * git add
* * git commit
* * git push (This updates the files and publishes the website on github.)


#### ~Documents/HostedWebsiteMarkdown

This is a work directory used to modify and convert the 'Document' Markdown files to html. It is also used to store potential 'Document' files.

* Add [TOC] at the top of <filename\>.md file if a local table of contents is needed.
* Convert <filename\>.md to <filename\>.html
* * md_to_html.py <filename\>.md
* Copy <filename\>.html to HostedWebsite directory.
* * **cp <filename\>.html ../HostedWebsite/.**

#### ~Documents/Prayer/familyTime

This directory contains the family_time.html app for the website. 

It also contains the content_version.md file which contains the text displayed by family_time.html and God_Within.html apps. If the content_version.md file is modified, both the  family_time.html and God_Within.html apps must be rebuilt.

* After making changes, create a new family_time.html by running ./build.sh
* Update remote repository.
* * git status
* * git add
* * git commit
* * git push (This updates the update the files on github.)
* Copy family_time.html file to HostedWebsite directory.
* * **cp family_time.html ../HostedWebsite/.**


#### ~Documents/Prayer/God_Within

This directory contains the God_Within.html app for the website.

Note that this app uses the content_version.md file from familyTime directory.

* After making changes, create a new God_Within.html file by running ./build.sh
* Update remote repository.
* * git status
* * git add
* * git commit
* * git push (This updates the update the files on github.)
*  Copy God_Within.html file to HostedWebsite directory.
* * **cp God_Within.html ../HostedWebsite/.**



