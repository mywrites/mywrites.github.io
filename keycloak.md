---
layout: default
title: "Keycloak"
category: "Identity Access Management"
---
Keycloak Single Sign On (SSO) is the Identity and Access Management (IAM) solution that allows you to access the Game Warden Web app, your products, and other Game Warden-hosted solutions more securely and using a single set of login credentials.

Game Warden Keycloak SSO integrates with the Platform One (P1) SSO. Both function similarly, allowing secure access to the same applications. This article provides insight into the Game Warden Keycloak SSO process, hereafter referred to as Keycloak SSO.

P1, a Department of Defense (DoD) counterpart to Game Warden, is a DevSecOps platform that delivers applications to the government. P1 also contains DoD-approved tooling for software development. Since Game Warden integrates with P1, our teams have access to this tooling along with several P1 solutions such as Big Bang (link removed) and Iron Bank (link removed). To use Keycloak SSO initially, you must first [Create a P1 SSO Account](https://login.dso.mil/). If you have both sets of credentials (P1 and Keycloak SSO), you can use either going forward since both provide access to the same applications.

Game Warden provides Keycloak SSO-protected customer environments.

## Establish Keycloak SSO

Prerequisites for Keycloak SSO access:

* Download a Multi-factor Authentication (MFA) application.
* [Create a P1 SSO Account](https://login.dso.mil/).

To establish Keycloak SSO:

![Keycloak](/img/keycloak1.png)

1. Access the **Keycloak Account** page (link removed).
1. Click **Sign in**.

    The system returns you to the **Game Warden** page.

1. Click **Log in w/P1 SSO**.
1. Enter your login credentials and proceed with Multi-factor Authentication (MFA).
    The system returns you to the **Keycloak Account** page. The **Sign in** button now reads **Sign out**, an indication that you have Keycloak account access. From the left navigation pane, **Signing in** is selected. This page also displays **Set up Password** (if you have never established a password, else **Update** displays) and **Set up authenticator application**. You must establish each.

1. Click **Set up Password**. 

   The **Logging in to Account Console** page opens.
1. Click **Accept** after reading and approving the conditions for use of a US Government (USG) Information System (IS).
1. Enter and confirm your new Keycloak SSO password then click **Submit**.

    The system returns you to the **Keycloak Account** page. The previous **Set up Password** reference now reads **Update**, allowing you to reset your password at any time.
 
1. Click **Set up authenticator application**.
   The **Logging in to Account Console** page opens.
1. Scan the QR Code, enter the 6-digit code, provide a **Device Name** (optional) then click **Submit**.

   The system returns you to the **Keycloak Account** page. As a matter of information, Keycloak SSO uses your **P1** username. This reference is visible from the **Personal Information** option in the left navigation pane. You have successfully established your Keycloak login credentials.

## Keycloak SSO Components
Keycloak SSO uses three primary components that work in unison as background processes to confirm user validity:

* Authentication Service (Istio’s Authservice software)
   * Verifies Game Warden users based on their login credentials.
   * For additional information, read **Authservice Documentation** (link removed).
   * For additional information, read **Architecture Overview** (link removed).
* JSON Web Token (JWT)
   * Shares information between devices, such as a client and a server. During this process, JWT    performs authorization to ensure the user requesting application access is the same user who provided login credentials during the authentication process. JWT receives the user profile from Authservice and, using public keys, verifies the login credentials to determine if the JWT sender (user) is safe for application access. In short, the client (browser/user) sends a username and password along with profile information gathered by Authservice to the server which, in turn, creates a JWT and assigns a secret only known to the JWT. At this point, the JWT contains user profile information, login credentials, and a secret. The server sends the JWT to the client. The client returns the JWT to the server. The server verifies that the JWT has not been altered, signaling that the user requesting application access is the same user who provided login credentials. If valid, the server grants application access. Since JWT stores all user information on the client, the user has application access.
   A JWT has three parts, each comprising specific data:

     **Header** – Sends data to and from the client. The header includes the token type, JWT, for example. It also includes the algorithm in use, such as “alg”: “HS256” (which works in conjunction with the Signature to verify users and is used to encode/decode data), and a token expiration date.

     **Payload** – Includes user information and any designated groups/roles. For example, the payload might include the sub or subject, such as the user ID. It also might include the username. 
   
     **Signature** – Reviews header and payload data before it is returned to the server to ensure the client has not altered this data. It also verifies the JWT sender (user) and, if valid, grants application access.
* Istio Sidecar
   * Manages network traffic and enforces policies, functioning as a traffic cop of sorts. The policies enable Istio Sidecar to allow or deny application access to users.

Below is a workflow diagram of the Keycloak SSO process:

![Keycloak](/img/keycloak3.png)
 
**NOTE**: <br/>
The diagram above references a Common Access Card (CAC), External Certification Authority (ECA), and a Federal Personal Identity Verification (PIV) card. These cards provide access to Game Warden-hosted secure applications in the Staging (STG) and Production (PRD) environments. 

**Content Removed**


