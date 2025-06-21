# Kali DHCP Server Lab Project

This project sets up a DHCP server inside a VirtualBox Kali Linux VM to assign IP addresses to a host Kali Linux machine.

## Project Setup

- Host OS: Kali Linux (Client)
- Guest OS (VM): Kali Linux (DHCP Server)
- Networking Mode: Host-only Adapter

## Configuration

- `dhcpd.conf`: The DHCP server configuration file.
- Screenshots: Setup screenshots located in the `screenshots/` folder.

## IP Address Scheme

- Gateway: `192.168.56.1`
- Range: `192.168.56.100` to `192.168.56.150`
- Subnet: `255.255.255.0`

## Steps

1. Installed Kali VM and configured VirtualBox networking (Host-Only).
2. Installed and configured `isc-dhcp-server`.
3. Used `/etc/dhcp/dhcpd.conf` to define IP range and DNS.
4. Verified successful dynamic IP assignment from VM to host using `dhclient`.
