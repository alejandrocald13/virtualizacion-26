# Homework 01 - Virtual Machine and Host Network Communication

## Objective
Configure a virtual server (VirtualBox) with an IP address belonging to the home network subnet, and establish a successful ping communication between the virtual server and the host machine.

## Requirements
- Configure the virtual server with an IP that belongs to the home subnet.
- Perform a ping from the virtual server to the host machine.

## Environment

| Item | Value |
|------|-------|
| Hypervisor | VirtualBox |
| Guest OS | Ubuntu Server |
| Network Adapter Mode | Bridged Adapter |
| Host OS | Windows 11 |

## Network Configuration

### Host Machine
Description of the host's network configuration (adapter, IP address, subnet mask, gateway).

Command used on Windows 11 (PowerShell or CMD):

```powershell
ipconfig
```

![LOCAL HOST IP WINDOWS 11](/docs/ip-host-windows-11.png)

```
Host IP: 192.168.0.197
Subnet Mask: 255.255.255.0
Gateway: 192.168.0.1
```

### Virtual Server
Description of the virtual machine's network configuration and how it was set to match the home subnet. In VirtualBox, the network adapter for the VM was set to **Bridged Adapter**, attached to the physical network interface used by the host, so the VM obtains an IP address within the same home subnet as the host.

![VM NETWORK CONFIGURATION](/docs/ubuntu-server-network-configuration-vm.png)


Command used on Ubuntu Server:

```bash
ip addr show
```

![VIRTUAL HOST IP WINDOWS 11](/docs/ip-virtual-ubuntu-server.png)

```
VM IP: 192.168.0.167
Subnet Mask: 255.255.255.0
Gateway: 192.168.0.1
```

## Ping Test

Ping executed from the virtual server (Ubuntu Server) toward the host machine (Windows 11) to verify connectivity.

```bash
ping 192.168.0.197
```

![PING SUCCESFULLY](/docs/ping-succesfully.png)

## Repository
- **GitHub Repository:** *https://github.com/alejandrocald13/virtualizacion-26*
- **Branch:** `hw-01`