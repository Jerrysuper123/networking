# networking
https://www.youtube.com/watch?v=fErDcUtd8fA

## Ip table
Ports - ssh 22, http 80, https 443
Ingress rules - In Oracle Cloud, your compute instance is placed within a subnet, which is part of a Virtual Cloud Network (VCN). Ingress rules are part of the network security rules that specify what kind of incoming network traffic is allowed to reach your instance. If the ingress rules are too restrictive (e.g., blocking the required ports), the necessary traffic won’t reach your instance. Configuring these rules correctly is essential.

## Subnet

Ip table - iptables is a utility in Linux that allows you to configure the rules that govern how your compute instance handles incoming and outgoing network traffic. Even if you’ve opened the necessary ports and configured the ingress rules in the cloud network, the iptables on the instance itself might still block traffic if not configured properly.

The typical challenge for beginners to Oracle Cloud is to allow network traffic to reach your compute instance. Try looking at opening the right ports and ingress rules for your subnet and managing the iptables on your compute instance


## What is subnet?

A subnet (short for "subnetwork") is a logically segmented portion of a larger network, such as a Virtual Cloud Network (VCN) in Oracle Cloud. It divides the network into smaller, manageable sections, each containing a range of IP addresses. Here’s how it works:
Key Points About Subnets:

Logical Division: A subnet is a segment of a larger network, defined by its IP address range. It allows for better organization, management, and security of network resources.
IP Address Range: When you create a subnet, you assign it a specific range of IP addresses (known as the CIDR block). For example, you might create a subnet with a range like 192.168.1.0/24, which includes IP addresses from 192.168.1.0 to 192.168.1.255.

Types of Subnets:
Public Subnet: Instances in a public subnet can directly access the internet because they are assigned public IP addresses.

Private Subnet: Instances in a private subnet do not have direct access to the internet. They are often used for more secure or internal-facing resources.

Isolation and Security: Subnets help isolate different parts of your network. For example, you might have one subnet for web servers (public) and another for databases (private), keeping sensitive data separate from public-facing components.

Routing and Firewalls: Subnets are associated with specific routing tables and security lists (or network security groups), which determine how traffic is routed and what traffic is allowed in or out of the subnet.

In the context of Oracle Cloud, when you launch a compute instance, you place it in a specific subnet, and the characteristics of that subnet (public or private, IP range, security rules) affect how the instance can communicate with other resources and the internet.

The statement refers to how IP address ranges are defined and managed within a subnet. Here’s a breakdown:

Understanding IP Address Ranges and Subnets:

IP Address: An IP address is a unique identifier assigned to devices on a network. In this context, we’re discussing IPv4 addresses, which are 32-bit numbers typically represented in decimal form as four octets separated by periods (e.g., 192.168.1.0).

CIDR Notation: 192.168.1.0/24 is an example of CIDR (Classless Inter-Domain Routing) notation. It’s a way to specify a block of IP addresses that belong to a subnet.
192.168.1.0: This is the starting IP address of the subnet, often referred to as the "network address."

/24: This indicates the subnet mask, which determines the size of the subnet. The /24 means that the first 24 bits of the IP address are fixed (they define the network), and the remaining 8 bits are available for defining individual host addresses within that subnet.

Calculating the Range:
192.168.1.0/24: In this case, the subnet mask /24 corresponds to 255.255.255.0 in traditional subnet mask notation. This leaves 8 bits (32 total bits minus the 24 fixed bits) for defining host addresses.

With 8 bits available, you can have 2^8 = 256 possible IP addresses.
The first address in the range, 192.168.1.0, is reserved as the network address, and the last address, 192.168.1.255, is reserved as the broadcast address. These are special addresses used for network management purposes.

The usable IP addresses in this subnet range from 192.168.1.1 to 192.168.1.254.

## Summary:
192.168.1.0/24 defines a subnet where the first 24 bits are fixed (the network part), and the remaining 8 bits can vary (the host part).
Range: The full range of IP addresses in this subnet is from 192.168.1.0 to 192.168.1.255.
Usable Addresses: The usable addresses for assigning to devices are from 192.168.1.1 to 192.168.1.254.
This allows network administrators to organize and manage IP addresses efficiently within a network, ensuring that devices have unique addresses and can communicate with each other properly.

