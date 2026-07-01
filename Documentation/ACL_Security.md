# Access Control List (ACL) Configuration

## Objective
Implement network security by restricting the Students VLAN from accessing sensitive network resources while allowing access to permitted resources.

---

## Security Policy

| Source VLAN | Destination | Action |
|-------------|-------------|--------|
| VLAN 30 (Students) | VLAN 40 (Admin) | Deny |
| VLAN 30 (Students) | VLAN 10 (Management) | Deny |
| VLAN 30 (Students) | VLAN 20 (Staff) | Permit |
| VLAN 30 (Students) | Internet | Permit |
| VLAN 10 (Management) | All Networks | Permit |
| VLAN 20 (Staff) | All Networks | Permit |
| VLAN 40 (Admin) | All Networks | Permit |

---

## ACL Information

- ACL Name: STUDENT_SECURITY
- ACL Type: Extended ACL
- Applied Device: R1-SCHOOL
- Applied Interface: GigabitEthernet0/0/0.30
- Direction: Inbound

---

## ACL Configuration

ip access-list extended STUDENT_SECURITY
 deny ip 192.168.30.0 0.0.0.255 192.168.40.0 0.0.0.255
 deny ip 192.168.30.0 0.0.0.255 192.168.10.0 0.0.0.255
 permit ip any any

interface GigabitEthernet0/0/0.30
 ip access-group STUDENT_SECURITY in
---

## Verification

### Successful Tests

- Student PC cannot access Admin VLAN.
- Student PC cannot access Management VLAN.
- Student PC can access Staff VLAN.
- Student PC can access the Internet Server.
- ACL is functioning as expected.

---

## Result

The Extended ACL successfully protects sensitive Management and Admin networks while allowing Students to access authorized resources such as the Staff VLAN and Internet. This implementation follows enterprise network security best practices.