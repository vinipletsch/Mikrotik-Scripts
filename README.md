# Mikrotik-Scrits

Dynamic DNS client service for Mikrotik routers

This script periodically checks your network’s IP address; if it sees that your IP address has changed, it sends (updates) the new IP address to your hostname in your Dynu account.

Uses secure mode with SSL DYNU API.

Steps: 

1 - Create a new scrit  "/system script add name=Dynu policy=read,write,test"; 

2 - Copy/paste the script;

3 - Verify that the script is added successfully by going to System then Scripts "/system script print";

4 - Create a new scheduler entry to run the script every X minutes: 
    - "/system scheduler add comment="Update Dynu DDNS" interval=Xm name=ddns_sheduller on-event=Dynu policy=read,write,test start-time=startup";

5 - Done!
