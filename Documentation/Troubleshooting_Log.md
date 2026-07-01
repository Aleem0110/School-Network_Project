Troubleshooting Log

Issue:
DHCP was not assigning IP addresses to client PCs.

Root Cause:
The SW-CORE port connected to R1-SCHOOL (Gi0/1) was not configured as a trunk port.

Resolution:
Configured the router-facing switch port as a trunk.

Result:
DHCP started working successfully.
Inter-VLAN routing was verified successfully.