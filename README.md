# **Dynode CRON for dynamic IP addresses**

Monitors the external IP address each minute, updates dynode.conf upon change and restarts the Dynode.


Information
-----------
The script must be ran as a 1 minute CRON job. 

The current IP address of the Dynode is pulled from the connected peers/nodes list and stored in an IP history file. Each minute the external IP address is compared with the contents of the IP history file, if the result differs to the previous result, then the new IP address is written to the Dynode.conf file. Once this change is written to Dynode.conf the dynamic daemon(dynamicd) is automatically shutdown safely and restarted.

Requirements
------------
The Dynode must be hot (local and contain the collateral) otherwise upon restart the Dynode will not autostart.

The CRON must be ran only on a machine running a single Dynode instance.

Linux ONLY.
