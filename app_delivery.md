---
layout: default
title: "Application Delivery Method"
category: "Policies"
---
This policy establishes a set of requirements designed to standardize application delivery methods; more specifically, this policy ensures there is a consistent, efficient, and secure method in place for moving applications from servers to user workstations. Citrix, located on the desktop, is the mechanism servers use to deliver applications – using the product: XenApp. The XenApp software allows the operation of all of our company's medical applications. The XenApp software, not visible to users, allows Citrix Administrators to access the application to troubleshoot issues. The Citrix XenApp and XenDesktop technologies are the primary methods for delivering applications to user workstations.

## Policy Statement
The *Citrix XenApp* policy identifies the requirements that must be satisfied to provide standard application delivery to user PCs and workstations.

## Terms
The following terms are specific to the *Application Delivery Method* policy:

| **Term**                            | **Description**                                        |
| ------------------------------------| -------------------------------------------------------|
| Citrix XenApp                       | Citrix, located on the desktop, is the mechanism servers use to deliver applications – using the product: XenApp. This software backend, not visible to users, allows Citrix Administrators to access the application to troubleshoot issues. The Citrix XenApp/XenDesktop technologies are the primary methods of delivering applications to user PCs and workstations. |
| Information Security Officer (ISO)  | Team member charged with developing, implementing, enforcing, and maintaining IT security standards for all data systems, thus ensuring there are no breaches and all information and patient data remain safeguarded. The ISO has a range of other responsibilities, such as performing audits, investigating security incidents, evaluating IT risks, and determining IT security policy and strategy. |
| Recovery Point Objective (RPO)     | Timeframe (maximum) within which data might be lost during an interruption of IT services. |
| Recovery Time Objective (RTO)      | Timeframe within which an interruption must be resolved before business cohesion is affected. |
| Systems Administration Group       | Under Technical Service Operations (TSO), this team is responsible for the management and oversight of storage devices, servers, and data centers. Daily responsibilities include (but are not limited to) resolving system errors, replacing parts, and reloading operating systems while also ensuring all data is protected and secure. Spelling out this team name is intentional. The team should not be confused with the Systems Assurance Group with the same acronym. |
| Systems Assurance Group (SAG)       | Under Technical Service Operations (TSO), this team reviews all hardware and software installations to ensure that each meets existing standards and that there is a formulated project plan in place prior to any installation. In brief, SAG ensures reliable, efficient, and compliant hardware and software installations. |
| Technical Service Operations (TSO)  | Department that supports the organization by maintaining daily IT operations. In addition, TSO enforces Occupational Safety and Health Administration (OSHA) standards to ensure all company data centers are secure work environments, while also making certain that the Health Insurance Portability and Accountability Act of 1996 (HIPAA) security requirements are satisfied. |

## Scope
**Redacted** recognizes the need to standardize application delivery methods as well as backend application support. The Citrix XenApp/XenDesktop technologies are the approved, tested, and primary methods of delivering the application experience to users. 

**Redacted** deploys hundreds of third-party and vendor-supplied health care software systems. For supportability, it is the company policy to require third-party, vendor-supplied software systems to adhere to a common set of industry standards that are tested and proven to function properly within the Citrix environment. For a third-party software vendor to be fully supported while operating in the Citrix environment, the third-party vendor must, first, meet these policies and continue to adhere to them. Failure to do so can result in the **Redacted** terminating vendor-application support for Citrix published resources that do not meet these minimum requirements.

## Procedures
The procedures delineated below must be followed to comply with the Citrix XenApp policy for data centers.
1. IT must provide a supported, current, and stable Windows XenApp server that meets the hardware and software requirements from the application vendor.
1. Citrix XenApp/Xen Server/XenDesktop hardware must be provided solely by TSO.  
1. IT support must require that any vendor application be compatible with a supported version of XenApp, Windows OS, and all components within the OS such that they meet IT application and security standards. In addition, as versions of the XenApp and Windows server operating systems become outdated and unsupported, IT support must have assurances, in writing, that a technical roadmap exists for upgrades and configuration changes for 5-year vendor support of any Citrix resource published in the Citrix environment.
1. All hardware attached to Citrix servers or workstations (using a Citrix receiver or resource) must, before deployment, be listed on the current Citrix/Windows/VMware compatibility matrix, which is available online. Attached hardware not on these compatibility matrices will not be supported in the Citrix environment.
1. XenApp software deployments must be performed in accordance with the best performance and reliability practices provided by Citrix Systems, Inc. for any current and supported versions of XenApp.
1. Administrative/root access to Citrix infrastructure devices (such as Server OS, Citrix Admin Console, and NetScaler) is not allowed without written approval from the Systems Assurance Group (SAG).
1. All vendor application software must be installed by the vendor (or a representative) onto XenApp servers. IT support must be readily available to provide needed system access to accomplish this task. Per **Redacted** IT support protocol, no configuration changes are permitted to the Windows OS that will compromise security or OS functionality. Any potential issues (to include the aforementioned changes) must be reviewed by SAG before any production system deployments are authorized.
1. Failure by the vendor to upgrade the application to support new releases of Windows Server OS, VMware, or Citrix XenApp will result in loss of support for the application by the IT staff. 
1. Any production application performance or reliability issue that occurs after a vendor application publication and deployment on a XenApp server must be the responsibility of the vendor to remedy. IT support will engage and make any necessary and reasonable changes to fix any application or reliability issue, only at the direction of the application vendor.
1. The vendor must provide any (and all) performance-enhancing solutions to satisfy the **Redacted** patient care providers and ancillary support staff requirements.
1. IT support will provide and maintain necessary backups and/or snapshots of these servers as a basic recovery plan. Detailed backup requirements from each vendor must be provided to ensure adequate recovery methods exist to recover any Citrix resource defined by the Recovery Point Objective (RPO)/Recovery Time Objective (RTO) requirements. 
1. All applications that are published through the XenApp tier must be approved by SAG and, when installed, be in full compliance with all requirements referenced in this document.

### Exceptions
Exceptions requests (or permission to deviate from any of the above-referenced procedures/requirements) must be submitted to SAG via completion of the *Systems Administration Change of Policy Request* form. This form is available on the corporate SharePoint site, and a copy may be emailed to users who are unable to access this document on the network. 

The completed *Systems Administration Change of Policy Request* form must contain signature approval from a Supervisor, Manager, Director, or Executive associated with the department from which the request originates. Upon form receipt, SAG will review the request. Exceptions that are granted will require the signed approval of all SAG members. Actions involving changes to the IT security standards also will require additional approval of the ISO. For example, a change in an Active Directory policy (which is security-related) would require the additional approval of the ISO.

Exceptions requests cannot be submitted by telephone or word-of-mouth, as these are unacceptable means of request submission.

SAG meets on alternate Tuesdays. For unique situations (where approval is required before the next scheduled meeting), group members may initiate a special meeting. 


**NOTE**:<br/>
If the requested change meets the compliance standards referenced in this document, the modification may be authorized by SAG and implemented in the **Redacted** Citrix environment. The approximate timeframe from the point the request is initiated to the actual approval/disapproval is 10 business days (for most requests) or as many as 30 days for more complex requests. If the request is rejected, SAG will provide an explanation which will include the restriction (operational/corporate/local/state/federal) that prevents request approval.

## Forms
Exception requests (or permission to violate any of the above-referenced procedures/requirements) must be submitted to SAG via completion of the *Systems Administration Change of Policy Request* form. This form is available on the corporate SharePoint site, and a copy may be emailed to users unable to access this document on the network. 

## Responsibilities
The implementation of this policy rests largely in the hands of members of the Systems Administration Group; however, all **Redacted** employees, contractors (to include persons or companies), and third-party entities/associates who perform work in the data centers (in any capacity) must comply with this policy. 

## Enforcement
To ensure compliance, TSO and ISO are responsible for enforcing this policy.

The Director of TSO and the Manager of the Systems Administration Group will verify compliance to this policy through various methods including, but not limited to, periodic walk-throughs, video monitoring, business tool reports, internal and external audits, and feedback to the policy owner.

All systems will be scanned at regular intervals to determine compliance of patch management. Any item found noncompliant will require immediate remediation. 

Users in violation of this policy may lose their privileges to log on to the network (as explained in the *Corporate Compliance* guidelines and the *Employee Handbook*); in addition, failure to comply with this policy may result in disciplinary actions (to include job termination).

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

