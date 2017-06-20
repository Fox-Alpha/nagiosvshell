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


Getting Started
---------------
Nagios V-Shell gets authorization information from the existing Nagios / Apache
access control mechanisms (usually a htpasswd.users file), as well as the 
cgi.cfg file for Nagios Core.  Most permissions for Nagios Core should be 
reflected in the Nagios V-Shell as well.  To get started, log into your Nagios 
webserver at http://<yourserver>/vshell, and enter your Nagios Core 
authentication information. Nagios V-Shell requires a valid user defined in 
the /path/to/nagios/etc/cgi.cfg file in order to display information for hosts and services.

NOTE: V-Shell needs a username from either an apache authentication method or the name 
need to be hard-coded into the index.php file.  See the code comments for the hard-coded option.  

V-Shell maintains most of the same features of Nagios Core, while utilizing 
a top menu bar for site navigation.  This is done to maximize space for table 
viewing for hosts and services.  

Nagios Core system commands, reports, and the Core interface can all be 
accessed by direct links from V-Shell. 


APC Caching
---------------
Nagios V-Shell is configured to automatically detect and use APC caching
if it installed.  APC caching caches object configuration data each time there is 
a change to the objects.cache file, and it caches status data based on the TTL 
config option in the vshell.conf file.  If TTL=90, V-Shell will cache data from
the status.dat file for 90 seconds before re-parsing the file.  This cache can be refreshed
at any time by selecting the "Refresh Data" link at the top right of the page. 


Authors
-------

Chris Laskey
Josh Soref
JAHunter
Scott Wilkerson
Mike Guthrie


Current Version
---------
The current version of V-Shell can be found at:

https://github.com/NagiosEnterprises/nagiosvshell

Other open source Nagios software can be found at:

https://github.com/NagiosEnterprises/


Getting Help
------------------
For problems, feedback, or support, use the V-Shell forum at the following address:
http://support.nagios.com/forum/viewforum.php?f=19
