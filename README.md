# EC2-proxy
This repo serves as a simple guide to use AWS EC2 servers as simple proxies for your internet browsing  
Proxy server used is Squid

## Setting Up Squid Server
Run these commands to install Squid server
```
sudo apt-get install squid3
```

## Move Squid Config File
Move squid config file (squid.conf) to /etc/squid and replace the existing file
```
sudo mv squid.conf /etc/squid/
```

## Restart Squid Server
Run these commands to restart Squid and verify status is ok
```
sudo service squid restart
sudo service squid status
```

## Open Up AWS Security Group
Open up port 3128 on your AWS EC2 inbound security group

## Setting Up Firefox
Configure Firefox to send a proxy through the EC2's server IP and specified port of 3128  
See https://support.mozilla.org/en-US/kb/connection-settings-firefox  
Server IP is to be placed in 'Manual Proxy Configuration' -> 'HTTP Proxy'  
Place port number 3128 in 'Port'

## Notes
Port number 3128 is arbitary and can be changed in the config file  
Do remember to update your AWS security group if you change your port to accept incoming connections from that port  
Do remember to pick a port that is not used by other services  