==========================
WAN CONFIGURATION
==========================

WAN Link:
ISP-RTR G0/0/0 ---> R1-SCHOOL G0/0/1

WAN Network:
10.10.10.0/30

ISP-RTR IP:
10.10.10.1

R1-SCHOOL IP:
10.10.10.2

Status:
WAN Connectivity Verified (Ping Successful)

Default Route:
R1-SCHOOL --> 0.0.0.0/0 via 10.10.10.1

Static Routes on ISP:
192.168.10.0/24
192.168.20.0/24
192.168.30.0/24
192.168.40.0/24



==========================
INTERNET SEGMENT
==========================

ISP Router Interface:
GigabitEthernet0/0/1

IP Address:
200.1.1.1/24

Internet Server:
Device Name: INTERNET-SERVER

IP Address:
200.1.1.2/24

Default Gateway:
200.1.1.1

Status:
ISP Router ↔ Internet Server Connectivity Verified (Ping Successful)