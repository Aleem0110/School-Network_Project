=========================================
NAT/PAT CONFIGURATION
=========================================

Project:
Enterprise School Network

Device:
R1-SCHOOL

-----------------------------------------
Purpose
-----------------------------------------
NAT (Network Address Translation) allows private IP addresses
to communicate with external networks.

PAT (Port Address Translation) enables multiple internal devices
to share a single public IP address by using different port numbers.

-----------------------------------------
NAT Type
-----------------------------------------
PAT (NAT Overload)

-----------------------------------------
Access Control List
-----------------------------------------
ACL Number: 1

Permitted Networks:

192.168.10.0/24 (Management)
192.168.20.0/24 (Staff)
192.168.30.0/24 (Students)
192.168.40.0/24 (Admin)

-----------------------------------------
Inside Interface
-----------------------------------------
GigabitEthernet0/0/0

-----------------------------------------
Outside Interface
-----------------------------------------
GigabitEthernet0/0/1

-----------------------------------------
Configuration
-----------------------------------------

access-list 1 permit 192.168.10.0 0.0.0.255
access-list 1 permit 192.168.20.0 0.0.0.255
access-list 1 permit 192.168.30.0 0.0.0.255
access-list 1 permit 192.168.40.0 0.0.0.255

interface GigabitEthernet0/0/0
 ip nat inside

interface GigabitEthernet0/0/1
 ip nat outside

ip nat inside source list 1 interface GigabitEthernet0/0/1 overload

-----------------------------------------
Verification Commands
-----------------------------------------

show ip nat translations
show ip nat statistics

-----------------------------------------
Verification Result
-----------------------------------------

✔ NAT/PAT configured successfully.

✔ School clients can access the Internet Server.

✔ HTTP service tested successfully.

✔ Client-to-Server connectivity verified.

-----------------------------------------
Status
-----------------------------------------

Completed Successfully.