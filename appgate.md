---
layout: default
title: "Appgate"
---

# Appgate SDP
Appgate Software-Defined Perimeter (SDP) is a Department of Defense (DoD)-approved authentication service. This Zero Trust solution provides secure access to DoD networks and associated data. Managed by the Platform One (P1) Cloud Native Access Point (CNAP) team, Appgate SDP provides a range of network security protections to include:

* Denying implicit trust to a single user, device, or application.
* Enforcing a verify then trust security approach to network access.
* Promoting Least Privilege, solely providing as-needed access to network resources.

P1 SSO also helps authenticate and authorize DoD network users. While you can browse IL2 without Appgate SDP access, you must – in some cases – use Appgate SDP to enter IL4+ environments. For IL5 access outside the NIPRNet boundary, you must also run compliance scripts.

## Info
The DoD uses **Non-Classified Internet Protocol Router Network (NIPRNet)** to manage unclassified information. If you use NIPRNet or NIPRNet VPN (such as Air Force Desktop Anywhere), you can access IL4 and IL5 without using Appgate SDP. DoD's P1 team requires that you use Appgate SDP if you do not use NIPRNet or NIPRNet VPN, as you cannot access IL4 or IL5 without using one of these options.

**NOTE**
As customers, it is critical to understand that CNAP allows secure access to Game Warden-hosted solutions at IL4 and IL5. As a reminder, P1 CNAP manages Appgate.

The implementation of Appgate and Palo Alto firewalls provides DoD-approved solutions that meet security controls, as referenced in sections 5.10.1.x of the Cloud Computing Security Requirements Guide (Version 1, Release 4).

For additional information, read Cloud Native Access Point.

## Installing Appgate SDP¶
To install and run Appgate SDP:
1. Download a Multi-factor Authentication (MFA) application.
1. Create a P1 SSO account.
1. Configure Government Access Card with P1 SSO Account.
1. Download Appgate SDP for Windows, macOS, or Linux PCs at Appgate SDP Client Download.
1. Install Appgate SDP on your PC, following the on-screen prompts.
   During the installation process, select **Use Profile Link** in the **Create Profile** window then copy the following link into the Profile Link field. You can hover over the end of this profile text below to access the Copy to clipboard function, enabling you to click to copy this text from this location and paste into the **Profile Link** field during Appgate SDP installation.

   appgate://connect.cnap.dso.mil/eyJwcm9maWxlTmFtZSI6IlBsYXRmb3JtT25lIC0gU1NPIiwic3BhIjp7Im1vZGUiOiJVRFAtVENQIiwibmFtZSI6InAxX3NwYSIsImtleSI6IjQ4ODUyMjc1OTk3YWE0YTkzNTdjYzA2OWYxYjNkNTI1ZGI3NWI2NTU1YjgzNGY3Njk3MDI0MzdlMGViNjg1NmMifSwiY2FGaW5nZXJwcmludCI6IjMxZTk4OTI2NGVmNDc0ZWU4ZTg3OGVhM2ZmM2M1NGQ3YzlhOTNkOWM4N2VlZmMyODFlMTM4NGJkZTIyYTZlYTEiLCJpZGVudGl0eVByb3ZpZGVyTmFtZSI6IlNTTyAtIFBsYXRmb3JtIDEifQ==

This P1 CNAP profile link downloads all required settings and allows access to the P1 **Login** page.

1.	Click **Submit** to finalize the new profile addition.
1.	Click **Connect to Appgate SDP** in the Profile Created window. <br/>
    Your browser opens the P1 **Login** page.
1.	Use your CAC/ECA login credentials or enter your P1 login credentials then click **MFA log in**.
1.	Enter the MFA verification code, if necessary.
1.	Click **Accept** after reading and approving the conditions for use of a US Government (USG) Information System (IS). <br/>
    Appgate installation and P1 access complete.
1.	Close the P1 window and access the now open and active **Appgate SDP** session, which displays your accessible environments.

    ![Appgate](/img/appgate.png)
    
1.	Navigate the environments you prefer.
1.	Exit Appgate SDP by clicking Sign Out or Quit from the Options menu, designated by three vertical dots at the top right of the session.
    * Click Sign Out. <br/>
        You are signed out of Appgate SDP. The session becomes inactive but remains visible.
    * Click Quit. <br/>
        The Appgate SDP session closes and becomes hidden.
1.	Re-open Appgate SDP at any time by clicking Sign in with Provider, which launches the P1 Login page.

Customers who do not access IL4+ via NIPRNet or NIPRNet VPN (such as Air Force Desktop Anywhere), must use Appgate SDP to access these environments. During this access, Appgate SDP must remain open and active.

