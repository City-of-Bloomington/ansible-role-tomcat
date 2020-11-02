City-of-Bloomington.tomcat
=========

Installs Tomcat along with common packages on Ubuntu using apt.  For COB, we *always* front tomcat with Apache.  This simplifies and standardizes how we configure SSL certs and firewall ports.

Dependencies
------------

* City-of-Bloomington.linux
* City-of-Bloomington.apache

Variables
---------
* tomcat_webapps - Directory to set up for hosting webapps

While the Ubuntu default is in `/var/lib/tomcat/webapps`; however, for COB, we use `/srv/webapps`.  This is because when reinstalling Ubuntu, `/var` gets wiped, deleting any webapps that were installed.  By putting our webapps in `/srv`, they survive OS reinstalls.

Example Playbook
----------------
```yml
---
- hosts: 'linux-tomcat'
  become: 'yes'
  roles:
    - 'City-of-Bloomington.tomcat'
...
```

Copying and License
-------
This material is copyright 2016 City of Bloomington, Indiana
It is open and licensed under the GNU General Public License (GPL) v3.0 whose full text may be found at:
https://www.gnu.org/licenses/gpl.txt
