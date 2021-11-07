## This repo helps in preparing for LFCE.
LFCE
- https://www.opsschool.org/unix_101.html
- https://www.safaribooksonline.com/videos/linux-foundation-certified/9780134774015/9780134774015-LFCE_01_01_06
- https://learning.oreilly.com/videos/linux-foundation-certified/9780134774015/9780134774015-LFCE_01_01_00
- https://github.com/rilindo/LFCE_Practice_Exams
- https://linuxacademy.com/linux/training/course/name/linux-foundation-certified-systems-engineer
- https://trainingportal.linuxfoundation.org/learn/course/linux-networking-and-administration-lfs211/
- [Youtube - Linux Foundation Ceritifed Engineer (LFCE)](https://www.youtube.com/watch?v=D0Xob4DGbFQ)

NETWORK
- http://www.tecmint.com/installing-network-services-and-configuring-services-at-system-boot/
- https://wiki.squid-cache.org/KnowledgeBase/TransparentProxySelectiveBypass

SECURITY
- https://www.coursera.org/learn/real-time-cyber-threat-detection/home/welcome
- http://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-sg-it-4/s1-firewall-ipt-fwd.html
- https://medium.com/information-and-technology/so-what-is-apparmor-64d7ae211ed
- [ Basic SELinux Troubleshooting in CLI ](https://access.redhat.com/articles/2191331)

STORAGE
- https://mariadb.com/kb/en/connecting-to-mariadb/


## Requirements

    Essential Commands 5%
        Use version control tools
        Manipulate file content programmatically
        Run commands on many systems simultaneously
        Install Linux Distribution

    Operation of Running Systems 18%
        Monitor, tune and troubleshoot system performance
        Update operating systems to provide required functionality and security
        Update the kernel and ensure the system is bootable
        Script automation tools to make work faster and more accurate
        Train team members on new technology or changes to existing systems
        Maintain systems via configuration management tools
        Maintain the integrity and availability of hardware
        Develop and test disaster recovery plans
        Support incident management for outages/trouble
        Produce and deliver reports on system use (processor, memory, disk, and network), outages, and user requests
        Monitor security and conduct audits
        Manipulate Linux system during the recovery process
        Use udev for device detection and management
        Configure and modify SELinux/AppArmor policies

    User and Group Management 10%
        Connect to an external authentication source
        Configure advanced PAM

    Networking 15%
        Monitor, tune and troubleshoot network performance
        Configure network traffic tunneling
        Configure a system to perform Network Address Translation
        Dynamically route IP traffic
        Implement advanced packet filtering

    Service Configuration 17%
        Implement and configure an HTTP server
        Implement and configure time synchronization server
        Implement and configure network logging server
        Configure a DHCP server
        Implement and configure an SMTP service
        Implement and configure the HTTP proxy server
        Configure host-based and user-based security for a service
        Implement and configure a centralized authentication server
        Implement and configure a PXE Boot server
        Implement and configure an authoritative DNS server

    Storage Management 10%
        Manage advanced LVM configuration
        Identify storage devices using block device attributes
        Manage Linux file system features and flags
        Implement and configure remote block storage devices
        Implement and configure network shares

    System Design and Deployment 25%
        Define a capacity planning strategy
        Conduct post deployment verifications
        Create and maintain software packages
        Create, configure and maintain containers
        Deploy, configure, and maintain high availability/clustering/replication

- https://training.linuxfoundation.org/certification/linux-foundation-certified-engineer-lfce/
- https://resources.linuxfoundation.org/LF+Training/LF_Training_WP_CertificationPrepGuide_October2018+(6).pdf


## Possible questions
**Tmux** can be used!
- https://linuxize.com/post/getting-started-with-tmux/


- rsyslog 4%
    change server tcp port

- FILE SYSTEM
    - Big pages setting 
    - many questions: give permission to directory /xxx/xxx 740 and all the files inside this directory 6xx
    - volumes 4%   
    Create different volumes in a volume group: mirrored, listed, striped  

- FILE MANIPULATION 3%  
    - extract info from a file and redirect to a second one (cut, sort, uniq, grep, awk)
    - sed: Question to do a lot of things with file manipulation, like delete all redundant lines, delete second column, and many more. 


- IPTABLES  
    Allow traffic from host X only on port Y ...
    Redirect traffic ...
	    
- DNS 10%  
    **Don't forget about /etc/default/bind9**
    - Bind9 double zones based on views (internals 10.250.0.2/24)
    - install bind
    - configure it so that at-least it's listening at lo 
    - create a policy at /etc/bind/zones for example.com

- NFS 10%  
    - create nfs share : give ro insecure access to network xx.xx.xx.xx. Give rw secure access to example.com
    - Mount a device with authentication.
    Ensure that the appropriate export option is set so that the root UID/GID is mapped to the anonymous UID/GID.  
    - Set up the share to ensure that files are created with default permissions of 664, and directories with default permissions of 775

- LDAP PAM  
    Permit the access by ldap to remote user creating automatically his home folder.

- MariaDB  
    fails to start: myisam-recover for all MyISAM tables and aria-recover
    - [mariaDB](mariadb.md)

- Git 
    clone repo in ssh, create branch, push and search in the logs

- Docker container with CPU limits
    - [docker.txt](docker.txt)
    - create a docker with nginx:xxx (docker was not installed)

- Configure load balancer - reverse proxy
    - [apache load balancer](https://httpd.apache.org/docs/2.4/mod/mod_proxy_balancer.html)

- build package pkgbuild
    - Degrade a package

- Configure OpenVPN

- LDAP server and clients

- Routing traffic

- Install Apache web server and configure SSL
    - change http and https ports

- APPARMOR  
    - One service can not start, resolve issue with Apparmor

- LXC containers
    - given a domain file, make it auto-bootable, change memory and cpu configs..

- Pam
    - configure pam ssh so that if user tries to login 5 time, it gets refused

- Firewall  
    - this one may not have to be done using firewall -> disallow user charlie to get or maybe send at tcp/portxxx on computer xxxxx. 
    - route traffic from port xxx at internet interface to ip address xx.x.x.x at port xx 

- Squid  
install squid and configure it to take configuration from squid-upstream and then maybe clone to squid-downstream

Ctrl + w , ctrl +alt + w wasn't working 

- udev  
    maybe: do somthing with /srv/xxxx. or maybe: create some drives

- systemd  
fix issues with mysql without modifying configuration files

- Packaging  
    - create deb package, tar was provided 
    - downgrade package cesxxxx to last version

- Samba  
create filesystem, create user xxxxx, allow that user

- Kernel
there's a kernel in /srv/xxxx, make it bootable or installable at bootup. 

- Email  
configure postfix: use /xxx/xxx.key to create certificate signing request and put it at /xxx/xxxx.  use same key and create self signed certificate and put it /xxx/xxx.  use that ssl key and certificate

- Random question
    -  failsafe to server xxxxxxx
    -  do it using only nginx or haproxy
