This file is needed to ensure that actually VPN forward packets, otherwise the computer and the server are only connected, but not communicating.

The file must be copied in /etc/ufw/ substituting the existing before.rules 

after that, the command: "sudo ufw allow 1194/udp" must be executed
