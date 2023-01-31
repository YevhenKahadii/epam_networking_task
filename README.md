# epam_networking_task
EPAM University Programs DevOps external course

Module – Linux Networking

The practical part of the Linux Networking module involves creating means Virtual Box network shown in Picture 1
![image](https://user-images.githubusercontent.com/106541199/215833337-7f0530aa-48c5-43ea-9879-0385504a8558.png)

                                         Picture 1
                                         
Network parameters:
Net1 192.168.0.0/24
Net2 10.87.7.0/24
Net3 10.2.87.0/24
Net 4 172.16.7.0/24
client1 lo: 172.17.17.1/24, 172.17.27.1/24




Host is the computer on which Virtual Box is running;

Server_1 (ubuntu_server_22.04) – A virtual machine on which the Linux OS is deployed. Int1 of this machine in "Network bridge" mode is connected to the Net1 network, that is, it is in the address space of the home network. The IP address of Int1 is set statically according to the address space, for example 192.168.1.200/24. Interfaces Int2 and Int3 are respectively connected in "Internal network" mode to networks Net2 and Net3.

Client_1 (ubuntu22.04) and Client_2 (centOS7) – Virtual machines running Linux (preferably different distributions such as Ubuntu and CentOS). The interfaces are connected in "Internal network" mode to Net2, Net3 and Net4 networks as shown in Figure 1.

The Net2 network address is 10.87.7.0/24

The address of the Net3 network is 10.2.87.0/24. The Net4 network address is 172.16.7.0/24.

WARNING! If the Net2, Net3, or Net4 address space overlaps with the Net1 address space, the corresponding address can be changed at your discretion.

 1. Configure static addresses on all interfaces on Server_1.
 2. Configure the DHCP service on Server_1, which will configure the Int1 addresses of Client_1 and Client_2
 3. Using the ping and traceroute commands, check the connection between the virtual machines and Explain the result.
WARNING! In order for packets to pass from Client_1 and Client_2 to the Internet (more precisely, to return from the Internet to Client_1 and Client_2), the Wi-Fi Router must configure static routes for Net2 and Net3 networks. If there is no such possibility, put the Int1 interface on Server_1 into NAT mode.

 4. On the virtual interface lo Client_1, assign two IP addresses according to the following rule: 172.17.17.1/24 and 172.17.27.1/24. Configure routing so that traffic from Client_2 to 172.17.17.1 goes through Server_1, and to 172.17.27.1 through Net4. To check, use traceroute.
 5. Calculate the common address and mask (summarizing) addresses 172.17.1.1 and 172.17.27.1, and the prefix should be as large as possible. Delete the routes set in the previous step and replace them with the combined route that should go through Server_1.
 6. Configure the SSH service so that Client_1 and Client_2 can
connect to Server_1 and each other. 7.

 7. Configure the firewall on Server_1 as follows:
    a) Allowed to connect via SSH from Client_1 and forbidden from Client_2

    b) From Client_2 to 172.17.17.1 the ping was successful, but to 172.17.27.1 it was not successful

 8. If the routing for Client_1 and Client_2 access to the Internet was configured in point 3, delete the corresponding entries. Configure NAT on Server_1 service in such a way that Client_1 and Client_2 ping the Internet
