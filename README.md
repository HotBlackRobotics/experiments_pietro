# experiments_pietro

Currently I am developing on this branch. The work is aimed at enstablishig a VPN channel between my personal computer and a remote server: ubuntu@ec2-34-253-203-81.eu-west-1.compute.amazonaws.com .

The next step will be to integrate ROS within this tunnel, in order to allow remote communication between ROS-based machines.

Useful sources:
http://www.allitebooks.com/mastering-openvpn/

the following will be used to build certificates and keys:
https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-16-04#step-1-install-openvpn


Up to 6/09:

to launch the VPN from the server, use the following command:

sudo systemctl start openvpn@server

where the @server indicates the name of the config file, stored as /etc/openvpn/server.conf that has be followed by the VPN


At the moment, there're two possible configurations both for server and client.

for the server:
  1) sudo openvpn --config /experiments_pietro/configuration-test/server-conf/server.conf
      that is following the book guide
      
  2) sudo systemctl start openvpn@server 
      that uses the config file /etc/openvpn/server.conf illustrated in https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-16-04#step-4-build-the-certificate-authority
      and saved in /experiments_pietro/server config/sever.conf

for the client:
  1) sudo openvpn --config /experiments_pietro/configuration-test/client-conf/client.conf
      that is following the book guide
  
  2)  sudo openvpn --config /experiments_pietro/client config/client1.ovpn
    illustrated in https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-16-04#step-4-build-the-certificate-authority
