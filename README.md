# nagiosvshell


The Nagios V-Shell is a web interface written in PHP that is designed to render
as valid XHTML and be fully styled and formatted using CSS classes, while 
maintaining the power of Nagios Core for issuing system and node commands. 
I'm no good at writing sample / filler text, so go write something yourself.

Prerequisites:  
-------------
V-Shell requires apache and php 5.x already installed in the system, as well as
php-cli if it's not already there. 

Installation
--------------
To install V-Shell, complete the following steps with root permissions:

1. Change to the temp directory, and download the latest V-Shell tarball:


    cd /tmp
    wget http://assets.nagios.com/downloads/exchange/nagiosvshell/vshell.tar.gz
    
2. Unzip V-Shell tarball:


    tar xzf vshell.tar.gz
 
3. Change to the newly made directory:
    
    
    cd /vshell
  
4. Verify the values in `config.php` are correct. Sensible defaults are included for RHEL/CentOS 6/7 and Debian 7, and should require no action.
5. Once the configuration values are verified, add execute permissions and run the install script:


    chmod +x install.php
    ./install.php

6. Copy the configured `vshell` directory to the directory your Apache server is configured to serve from (for this example, we will use the default directory for CentOS 6/7):


    cp -R /tmp/vshell /var/www/html/
    
7. To access your V-Shell interface, navigate to `<vshell_server_ip>/vshell`    
    




After running this script, be sure to verify the location of the files
specified in the `/etc/vshell.conf` file, as well as the location of the
htpasswd.users file that is specified by your apache configuration.
    
These will be required in order for V-Shell to run correctly.

For problems or support, use the V-Shell forum at the following address:
http://support.nagios.com/forum/viewforum.php?f=19



APC Caching
--------------
V-Shell takes advantage of the Alternative PHP Cache system (APC), which is 
of particular importance if you are managing a large installation.  For 
information about APC and installation instructions see 
  http://php.net/manual/en/book.apc.php
  
  RHEL/CentOS/Fedora: yum install php-pecl-apc php-pecl-apc-devel
  Ubuntu/Debian		: sudo apt-get install php-apc
  
You may need to increase your PHP 'memory_limit' setting in your system's php.ini file
if you're using APC.  For large systems try a setting as high as 256-512MB.  


Current Version
---------
The current version of V-Shell can be found at:

https://github.com/NagiosEnterprises/nagiosvshell

Other open source Nagios software can be found at:

https://github.com/NagiosEnterprises/

Authors
-------

[Chris Laskey](https://github.com/chrislaskey)
[Josh Soref](https://github.com/jsoref)
[JAHunter](https://github.com/jahunter)
[Scott Wilkerson](https://github.com/scottwilkerson)
[Mike Guthrie](https://github.com/mguthrie88)
