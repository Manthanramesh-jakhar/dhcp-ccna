# dhcp-ccna
Practical CCNA networking project covering DHCP configuration, IP addressing, network fundamentals, and hands-on lab implementation.
# DHCP CCNA Networking Project

## Project Overview
This project demonstrates the practical implementation of DHCP (Dynamic Host Configuration Protocol) using Cisco networking concepts.

## Objectives
- Understand DHCP fundamentals
- Configure DHCP on a Cisco router
- Assign IP addresses automatically to clients
- Understand IP addressing and subnetting
- Verify DHCP connectivity and configuration

## DHCP Configuration

```bash
Router> enable
Router# configure terminal

Router(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.10

Router(config)# ip dhcp pool LAN
Router(dhcp-config)# network 192.168.1.0 255.255.255.0
Router(dhcp-config)# default-router 192.168.1.1
Router(dhcp-config)# dns-server 8.8.8.8

Router(dhcp-config)# exit
Router(config)# interface gigabitEthernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# end
Router# write memory
