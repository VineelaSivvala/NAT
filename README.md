# NAT
This repository is about creating NAT using Linux Network Namespaces.
# Network Namespace Configuration with NAT and Port Forwarding

## Table of Contents
1. [Introduction](#introduction)
2. [Setup Overview](#setup-overview)
3. [Challenges Faced](#challenges-faced)
4. [Bonus Tasks](#bonus-tasks)
5. [Conclusion](#conclusion)

## Introduction
This README documents the setup of a network using Linux namespaces to simulate a private organization with two clients. The configuration includes NAT (Network Address Translation) to allow clients to access the public network and port forwarding to enable access to an internal web server from the public network. Additionally, measures to restrict external traffic were implemented.

## Setup Overview
The setup involves:
- Two clients in a private organization (IP addresses: `10.0.1.2` and `10.0.1.3`).
- A router (using a bridge interface) to connect the clients to the public network.
- A public network with a public IP address (`203.0.113.1`).
- Port forwarding to an internal web server hosted on one of the clients.

### Network Topology
The network consists of:
- Client 1 (192..168.10.2) connected to the router.
- Client 2 (192.168.10.3) connected to the router.
- Router interfaces connected to both clients and the public network.
- Public network with a public IP address (203.0.113.2).

## Challenges Faced
During the configuration, several challenges were encountered:
- **NAT Configuration**: Ensuring proper NAT rules were established to facilitate communication between private and public networks.
- **IP Address Management**: Assigning unique IP addresses to interfaces while maintaining the correct subnetting to avoid conflicts.
- **Port Forwarding**: Setting up port forwarding correctly to allow access to the internal web server from the public network.
- **Restricting External Traffic**: Implementing firewall rules to limit unwanted access from the public network to the internal clients.

## Bonus Tasks
1. **Port Forwarding**: A simple web server was hosted on Client 1. The configuration was set up to forward requests from the public IP address (`203.0.113.1`) to the internal web server on Client 1, allowing external access to the web service.
2. **Restricting External Traffic**: Additional firewall rules were implemented using `iptables` to restrict access to only specific ports and IP addresses, enhancing the security of the internal network.

## Conclusion
This setup successfully demonstrates the use of Linux namespaces to create isolated network environments, enabling complex networking scenarios such as NAT and port forwarding. The challenges encountered provided valuable insights into network management and security practices. Future improvements could include additional security measures and further optimization of the network configuration.

