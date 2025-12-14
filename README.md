# openvpn-windows11-vm-lab
Hands-on lab configuring and verifying OpenVPN on Windows 11 in a VirtualBox virtual machine, including DNS, IP, and tunneling verification.
🔐 OpenVPN Configuration & Verification on Windows 11 (Virtual Machine)
📌 Overview

This lab demonstrates the installation, configuration, and verification of an OpenVPN client on a Windows 11 virtual machine.
The goal was to establish a secure VPN tunnel, observe network changes, and understand how VPNs affect IP addressing, DNS, and routing in a virtualized environment.

🎯 Objectives

Install OpenVPN Community Edition on Windows 11

Import and authenticate a VPN configuration file (.ovpn)

Establish an encrypted VPN tunnel

Verify VPN functionality using Windows networking tools

Understand DNS and IP changes when a VPN is connected

🧪 Lab Environment

Host OS: Windows

Hypervisor: Oracle VirtualBox

Guest OS: Windows 11 (x64)

VPN Client: OpenVPN Community Edition 2.6.x

VPN Provider: VPNBook (OpenVPN)

🛠 Tools & Technologies

OpenVPN GUI for Windows

VPNBook OpenVPN configuration files (.ovpn)

Windows Command Prompt (ipconfig)

VirtualBox networking (NAT)

🧾 Procedure
1️⃣ Install OpenVPN

Downloaded OpenVPN Community Edition (x64 / amd64)

Installed using default settings

Confirmed installation of TAP/Wintun virtual network adapters

2️⃣ Import VPN Configuration

Downloaded OpenVPN configuration files from VPNBook

Imported vpnbook-uk205-tcp80.ovpn into OpenVPN GUI

3️⃣ Authenticate & Connect

Entered VPNBook credentials

Successfully established a VPN connection

Received confirmation:

“Initialization Sequence Completed”

🔍 Verification & Results
VPN Connection Confirmation

VPN Status: Connected

Assigned VPN IP Address: 10.12.0.10

Network Adapter Verification (ipconfig)

A new virtual network adapter appeared after connection:

Adapter: TAP-Windows Adapter V9

IPv4 Address: 10.12.0.10

Subnet Mask: 255.255.255.252

DNS Servers:

213.186.33.99

91.239.100.100

This confirms:

Successful VPN tunneling

IP assignment by VPN DHCP

DNS redirection through the VPN

🧠 Technical Explanation
Why the IP Address Changed

The VPN server assigned a private IP address from its internal network.
This IP exists only inside the encrypted tunnel.

Why DNS Servers Changed

When the VPN connected, Windows accepted DNS servers pushed by the VPN provider.
This prevents DNS leaks and ensures all name resolution happens inside the VPN tunnel.

Why a New Adapter Appeared

OpenVPN creates a virtual network adapter (TAP/Wintun) that behaves like a physical NIC.
All VPN traffic is routed through this adapter.

Why This Works in a Virtual Machine

A virtual machine has its own:

Operating system

Network stack

Drivers

From the network’s perspective, the VM is a separate computer, so VPNs function normally.

📚 Key Concepts Demonstrated

VPN client vs VPN server

Encrypted tunneling

Virtual network adapters

DHCP & DNS over VPN

VPN behavior in virtualized environments

✅ Skills Gained

Installed and configured OpenVPN on Windows 11

Imported and authenticated VPN profiles

Verified VPN connectivity using networking tools

Analyzed DNS and IP changes caused by VPN tunneling

Applied networking concepts in a virtual machine

🏁 Conclusion

This lab successfully demonstrated how a VPN operates on Windows 11 within a virtual machine.
By verifying IP, DNS, and adapter changes, the lab confirms correct VPN configuration and deepens understanding of secure network tunneling.
