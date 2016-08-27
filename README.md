sa-tomcat
=========

[![Build Status](https://travis-ci.org/softasap/sa-tomcat.svg?branch=master)](https://travis-ci.org/softasap/sa-tomcat)

see box-example for deployment demo

Important: for ubuntu 14.04 LTS latest available packages are currently for tomcat7.
For 16.04 LTS normally available is tomcat8


```

---
- hosts: www

  vars:
    - root_dir: ..
    - my_tomcat_users:
      - {
         name: admin,
         password: admin,
         roles: "admin,admin-gui,manager-gui"
        }

  pre_tasks:
    - debug: msg="Pre tasks section"

  roles:
     - {
         role: "sa-tomcat",
         option_install_java: true,
         java_version: 8,
         tomcat_version: 7,
         tomcat_users: "{{my_tomcat_users}}"
       }


  tasks:
    - debug: msg="Tasks section"


```

