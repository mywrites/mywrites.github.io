---
layout: default
title: "Self-Service Guide"
category: "Cloud"
---
**CONTEXT**: I created this content for a cloud solutions company that needed technical and non-technical self-service documentation, enabling users to select their virtual assets (OS, storage, memory), execute reports, and determine payment options in this cloud environment.

## Infrastructure as a Service (IaaS)
IaaS allows you to outsource computing hardware (storage, servers, and network components). You can access this equipment via our cloud and pay for this computing hardware on a pay-as-you-go basis. We own the equipment and are responsible for all computing hardware maintenance, upgrades, and troubleshooting.

![IaaS](/img/cloud_ss.png)

IaaS provides the option of choosing from three cloud computing service models, contingent upon your business needs:

* **Public Cloud**
  * **Redacted** hosts the cloud service, using the same enterprise-grade infrastructure that supports all of our company systems. With the public cloud, we can manage your cloud infrastructure. The hardware is in data centers.
* **Private Cloud**
  * You host the cloud service. Unlike the public cloud service, the private cloud is not shared by other tenants. You are the sole tenant. You house the hardware which, generally, is in an on-premises location.
* **Hybrid Cloud**
  * A cloud service that uses public and private cloud offerings, giving the flexibility to tailor the services you consume to meet your requirements. For example, it is common for companies to use on-premises equipment (private cloud), extending the IT infrastructure to an off-premises location and shared equipment (public cloud) when there is unexpected growth or expansion.

The IaaS category contains the Compute, Storage, and Bundles subcategories.

## Compute
The **Compute** window allows you to create and view your virtual machines (VMs). A VM is an emulation of a computer system and can run different operating systems on a host computer. While your computer may have the MS Windows operating system, you can install a VM manager (such as Virtual Box or VMware) to add the Linux and Mac operating systems; all hosted on a single computer. This use is helpful if you need to test applications on different operating systems, or if you need to run older applications. With **Redacted** Cloud, when you create a VM, you become a host and, thereby, have access to a *slice* of a larger physical machine. The VM behaves like a desktop. Each VM has a corresponding external IP address and, using this address, you can connect to your VM via Remote Desktop. You can move your application server and MySQL database, for example, to this VM. Your VM can be replicated on other hosts. These hosts physically may be in the same data center OR different data centers in different geographic locations, based on the services you select/purchase.

The **Compute** window contains the **Name**, **Num CPU**, **Memory**, **Disk**, **OS**, **IP Address**, and **Status** columns. This window contains the **Create** button, the **Actions** drop-down list box, and the **Refresh** link.
1. Click the **Create** button to add a VM.
    
    The **Create Your New Virtual Machine** window opens. You also can access this window by clicking the **Create VM** button from the **Dashboard**. Here, you can select your operating system, configure a VM instance, and review cost information.
1. Click the **Select** button that corresponds with your preferred option relative to your operating system choice.
    
    The system adds the operating system that you selected to the right pane, impacting the calculation.
1. Enter values in the **Server Name**, **CPU Cores**, **Memory (in GB)**, and **Storage (in GB)** fields to configure your instance.
    
    Configuring the instance allows you to associate attributes with this new VM, such as the device name and corresponding storage amount. The VM instance represents the server itself. CPU cores represent the number of tasks the CPU can perform simultaneously.
1.	Click the **Create Instance** button to save your specifications.

    A new row now appears in the **Compute** window, based on the values you entered.
1.	Click the checkbox associated with the VM you want to adjust.
1.	Click the **Actions** drop-down list box and select the modification.
    
    The action you select will be enacted upon the server you identified via your previous checkbox selection.
1.	Click the checkbox associated with the server you want to adjust and select **Stop** from the **Actions** drop-down list box.
    
    A system message appears indicating that the server has been stopped. The color of the circular image in the **Status** column changes from green to red.
1.	Click the checkbox associated with the server you want to adjust and select **Start** from the **Actions** drop-down list box to restart the server.
    
    A system message appears indicating 
    that the server has started. The color of the circular image in the **Status** column changes from red to green.
1.	Click the **Refresh** link to ensure you are viewing updated information.


