---
layout: default
title: "Cloud Infrastructure"
category: "Cloud"
---
**Redacted** is an Amazon Web Services (AWS) partner and leading cloud solutions company, providing managed hosting along with a range of IT services and infrastructure support for businesses in the U.S. and abroad. 

To provide its clients with complete access to their cloud resources, the product allows clients to access their cloud platform assets, perform routine tasks, monitor services, view reports, and make payments independent of customer representatives. 

From virtual servers to storage devices and support tickets to pricing tools, the product provides a range of information and services to keep clients abreast of the activity in their cloud environments. With three cloud computing service models from which to choose (public cloud, private cloud, and hybrid cloud), clients can select the cloud offering that is most aligned with their business objectives. 

**Redacted**

## Overview
This document provides insight into the underlying product framework. Specifically, this document describes the internal components that comprise this new cloud environment, while using text and detailed images to explain and depict how these entities function.

This document audience includes system administrators and engineers who need to understand the cloud infrastructure.

**Redacted**

## Infrastructure 
The primary purpose of the infrastructure is to:
* Provide a secure multi-tenant environment for prospective clients at multiple geographic sites.
* Render a flexible infrastructure, adjusting to the growth and change aligned with business requirements.
* Ensure an easy-to-manage solution, which maximizes time and effort.
* Simplify management views, resulting in timely resolutions and troubleshooting.

## Terms 
While a *Glossary of Terms*, when included in technical documentation, is commonly located at the end of a manual, the placement of significant terms in this guide has been intentionally positioned near the beginning of this document to ensure you understand specific terminology.

| **Terms**                 | **Descriptions**                                                     |
| --------------------------|---------------------------------------------------------------------|
| Blade Server              | Unlike the rack-mounted server, the blade server is housed in a chassis. The blade server is smaller and requires less energy. This server needs less space and reduced cooling/air-conditioning. |
| Chassis                   | Container-like device or enclosure that houses blade servers. Commonly, eight servers can fit into one chassis. Twenty chassis devices can be routed into a single Fabric Interconnect, which handles connectivity to data center networks and storage components. The chassis devices collectively can house up to 160 blade servers.|
| Compute Cluster           | The Compute Cluster is the grouping or space where public and private cloud machines reside. Commonly, these computers work together to perform larger tasks, which they can do at a faster rate. All compute resources for clients are part of the Compute Cluster. The Compute Cluster ESXi hosts are connected to additional distributed switches; all explained further in this document: ESXi Host Switch, ESXi Host, vMotion, iSCSI-A, iSCSI-B, Replication, VTEP (VXLAN Tunnel End Point) |
| Distributed Switch        | Device that helps computers share network connections, and automates and centralizes the management of virtual machine (VM) networking in a vSphere environment. It can centralize switching for an entire data center. When adding new hosts, the distributed switch, commonly referred to as the vSphere Distributed Switch or VDS, standardizes network configuration. This makes it easier and faster to add new servers to our cloud environment. |
| Edge Cluster              | Computers that work close to where data is required. The Edge Cluster consists of two ESXi hosts and are connected to five distributed switches:  ESXi Host Switch for host management, ESXi Host vMotion, Replication, VTEP, EDGE   |
| Enhanced vMotion Compatibility (EVC) Mode | A state that exists when all host computers in a cluster, for example, use computer chips from the same manufacturer. All chips may be AMD, for instance, or all chips may be Intel. | 
| ESXi                      | Name or type of the VMware hypervisor used in the **Redacted** cloud environment. The ESXi hypervisor is the layer that separates the host machine from the virtual computer or guest machine, similar to helping multiple computers run inside of a larger one. |
| Fabric Interconnect        | Connects multiple computers or servers, helping them share information. Fabric Interconnect manages the connectivity to the data center networks. The chassis, which houses blade servers, connects to the Fabric Interconnect via I/O modules. The Fabric Interconnect, in turn, connects to the data center networks and storage components. Fabric Interconnects are commonly used in pairs (Interconnect Fabric A and Interconnect Fabric B, for example). |
| Fiber Channel (FC) Connectivity | Like Ethernet connectivity, fiber channels are used to transmit data quickly, simply, and affordably, particularly when sending data between computers and storage devices. |
| Fiber Channel Switches | A network switch (in *traffic cop* mode)that enables and directs data to move quickly between computers and storage devices via the Fiber Channel. |
| High-Availability (HA) Cluster | A group of computers that function as a single entity, commonly used to provide backup and fail-over, making these computers continuously available and accessible. |
| Hypervisor     | Software layer that separates the host machine from the virtual computer or guest machine. Multiple VMs can run on a single hypervisor. The hypervisor creates an environment to build VMs and virtual servers. Specifically, our infrastructure uses the ESXi hypervisor. ESXi is the hypervisor made by VMware. ESXi is VMware’s bare metal hypervisor.  |
| Link Aggregation Control Protocol (LACP) | Combines sevral network connections into a single, stronger one and improves switch bandwidth and throughput. LACP also provides or increases port redundancy. If one port fails or goes down, there will be another port on which to communicate. |
| Management Cluster | The Management Cluster consists of three ESXi 6.5 hypervisor nodes. The purpose of this cluster is to control management functions and provide compute resources for all management VMs. All client VMs are separate, and any failure of compute resources does not impact management machines. Any modification that is conducted on the Management Cluster does not impact the other cluster instances. The Management Cluster is connected to virtual distributed switches: ESXi Host Switch, VM Management, ESXi Host vMotion |
| Network Interface Card (NIC) | Device used to connect computers to networks. |
| Node   | Designation given to the computer or servers in a cluster or larger network. |
| SAN Switch   | A SAN switch is commonly a Fiber Channel (FC) switch, which is a network switch aligned with the fiber channel protocol used to transmit data for storage. This switch can examine and evaluate data or data packets, determine where this information is coming from (origin) and where it is being transmitted (destination), and it can send this information to its designated storage component. |
| Unified Computing System (UCS) | A Cisco system comprised of several components including switches, cables, and servers, operating under a single management umbrella. This system combines computers, storage, and network connections.|
| Uplink  | Connection that can send data across networks. |
| vCenter | The entity that manages the ESXi hypervisor along with computers and servers in a network. |
| Veeam | Backup and recovery software built for virtualization. This software is touted as easy-to-use data protection designed specifically for VMs. |
| vMotion | Component that allows you to move active and running VMs from one ESXi host to another with no downtime. |
| VMware | Software that allows you to run different operating systems (guests) inside an existing operating system (host). The company, itself, develops this software by the same name to manage virtual computers. |
| VMware vSphere | VMware’s virtual computer solutions which include ESXi hosts, storage, vCenter, and networking components, which manage virtual computers. |
| Zerto | The company uses Zerto software to perform and manage disaster recovery throughout the cloud platform. 

## Hardware Components (Physical Infrastructure)
While we have data centers in New Jersey and Colorado, the two primary data centers are in Reading, PA (East) and Salt Lake City, UT (West). Our team provides Disaster Recovery as a Service (DRaaS) by storing your data on servers in data centers, hosting and replicating this data such that failover is in place, which ensures that data remains available on other servers should one server be deemed inactive due to a catastrophe, for example. The cloud solution provides local redundancy, storing your data on servers in the East Coast or West Coast data center. This will depend on your location and service plan type. Within this single East Coast or West Coast data center, your data is replicated on different machines within this single facility. As a premium service, we provide global redundancy, replicating your data between data centers in different geographic locations. 

The physical infrastructure consists of the following hardware at two sites:

1. Cisco Unified Computing System (UCS)
   * 5108 Chassis
   * Cisco UCS Blade Servers (M3 and M4 Series with Intel Chipsets)
   * One Pair of Fabric Interconnects
1. Cisco Nexus 5K Switches
1. One Physical Veeam Server
1. One Pair of Brocade 6505 SAN Switches
1. Fortinet 3000D Series Firewalls

The environment currently is connected at 10G Ethernet with separate fiber channel (FC) switches for SAN storage and FC connectivity, as depicted in the image below.

**Redacted**

## Software Components
### VMware vSphere Hypervisor
The VMware infrastructure is divided into three separate clusters, each host running VMware Hypervisor version 6.5 with one vCenter server in a High-Availability (HA) cluster managing the infrastructure. 

This design provides a modular infrastructure that can be expanded or collapsed, contingent upon business needs. This design also attempts to control costs. For example, as compute requirements change, individual blade servers can be added or removed, and memory increased or decreased.

The hypervisor components are divided into three sections and connected to distributed switches:
1. Management 
1. Compute
1. Edge

**Redacted**

## Infrastructure Products
The infrastructure design uses VMware and other products to include:

* VMware ESXi Hypervisor (Version 6.5)
* VMware vCenter 6.5
* VMware Operations Manager
* VMware Log-Insight
* VMware vCloud Director
* VMware NSX 6.3
* Veeam Backup and Replication
* Zerto Replication

**Content Removed**

<style>
  table {
    width: 100%;
    border-collapse: collapse;
  }
  th, td {
    border: 1px solid black;
    padding: 8px;
    text-align: left;
  }
</style>

