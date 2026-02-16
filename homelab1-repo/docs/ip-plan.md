# IP Plan & Addressing

- Subnet: `192.168.5.0/24`
- Gateway: `192.168.5.1` (adjust if different)
- DHCP Range (example): `192.168.5.100 - 192.168.5.200`
- Static management IPs:
  - UDM Pro — `192.168.5.12`
  - USW-24-POE — `192.168.5.23`
  - Hypervisor — `192.168.5.3`
  - VMs — `192.168.5.4` – `192.168.5.11`

> Tip: Reserve all static IPs in UDM DHCP so ARP/NDP remains consistent.
