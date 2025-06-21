# Kali DHCP Server Project

This project demonstrates how to set up and configure a DHCP (Dynamic Host Configuration Protocol) server on Kali Linux using `isc-dhcp-server`. The DHCP server is hosted in a VirtualBox VM and provides IP addresses to DHCP clients in an isolated lab network using a host-only adapter.

## What This Project Covers

- Installing and configuring `isc-dhcp-server` on Kali Linux
- Writing a custom `dhcpd.conf` file
- Setting up a virtual lab using VirtualBox with host-only networking
- Testing DHCP client behavior from the host system
- Troubleshooting using tools like `ip`, `dhclient`, `systemctl`, and `journalctl`

## Lab Setup

### Environment

| Component     | Details                     |
|---------------|-----------------------------|
| Host OS       | Kali Linux                  |
| VM OS         | Kali Linux (GUI)            |
| Hypervisor    | VirtualBox                  |
| Network Type  | Host-only Adapter (vboxnet0) |

### Network Roles

- DHCP Server: Kali VM (VirtualBox)
- DHCP Client: Host Kali Linux

## Folder Structure

```
KaliDHCPServer/
├── dhcpd.conf              # DHCP server configuration file
├── README.md               # Project documentation
└── screenshots/            # Setup and test result screenshots
    ├── step1.png
    ├── step2.png
    └── ...
```

## Key Configuration

Sample `dhcpd.conf` file:

```conf
subnet 192.168.56.0 netmask 255.255.255.0 {
  range 192.168.56.10 192.168.56.100;
  option routers 192.168.56.1;
  option domain-name-servers 8.8.8.8;
  default-lease-time 600;
  max-lease-time 7200;
}
```

## Testing and Validation

- Verified that the host machine (client) received an IP address from the DHCP server
- Used `ip addr`, `ip neigh`, and `dhclient` to monitor interface behavior
- Ensured `isc-dhcp-server` ran correctly and responded to client requests
- Screenshots of the DHCP configuration and IP assignment are in the `screenshots` folder

## Notes

- Ensure the host-only adapter is enabled and configured properly in VirtualBox
- Turn off Wi-Fi on the host during testing to prevent interference from other DHCP servers (e.g. home router)
