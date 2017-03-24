# **Dynode CRON for dynamic IP addresses**

This monitors the external IP address each minute and updates dynode.conf upon changing.


Information
-----------
The script must run as an 1 minute CRON job. 

The current IP address of the Dynode is pulled from the connected peers/nodes list and then compared with the content of the IP history file, if the result differs to the previous result then the new IP address is written to both the IP history file and to Dynode.conf

Once this change is written to Dynode.conf the dynamic daemon(dynamicd) is automatically shutdown safely and restarted.

The Dynode must be hot (local and contain the collateral) otherwise upon restart the Dynode will not autostart.

The CRON must be ran only on a machine running a single Dynode instance.
