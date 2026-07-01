# DHCP Configuration

## DHCP Pools

### MANAGEMENT VLAN
Network: 192.168.10.0/24
Gateway: 192.168.10.1
DNS Server: 8.8.8.8

### STAFF VLAN
Network: 192.168.20.0/24
Gateway: 192.168.20.1
DNS Server: 8.8.8.8

### STUDENTS VLAN
Network: 192.168.30.0/24
Gateway: 192.168.30.1
DNS Server: 8.8.8.8

### ADMIN VLAN
Network: 192.168.40.0/24
Gateway: 192.168.40.1
DNS Server: 8.8.8.8

## Excluded Addresses

192.168.10.1 - 192.168.10.20

192.168.20.1 - 192.168.20.20

192.168.30.1 - 192.168.30.20

192.168.40.1 - 192.168.40.20

## Verification

All PCs successfully received IP addresses using DHCP.