# Azure Virtual Desktop & Hybrid Identity

Enterprise-style Azure Virtual Desktop (AVD) lab integrating Active
Directory Domain Services with Microsoft Entra ID, a multi-session
Windows environment, and persistent user profile storage.

## Project Overview

This hands-on lab demonstrates an Azure Virtual Desktop environment
built around hybrid identity and centralized virtual desktop delivery.

The environment connects Active Directory Domain Services (AD DS) with
Microsoft Entra ID through AD Connect Sync. A domain controller and an
AVD session host are deployed on separate subnets within the Azure
virtual network, while profile storage supports persistent user profiles
for the virtual desktop environment.

The project was built to develop practical experience with Azure
administration, hybrid identity, desktop virtualization, networking,
access control, and profile management.

## Architecture

The architecture separates the domain controller and Azure Virtual
Desktop resources into dedicated subnets within the same virtual
network.

-   **Microsoft Entra ID** provides cloud identity services.
-   **AD Connect Sync** connects the Active Directory environment with
    Microsoft Entra ID.
-   A dedicated **DC subnet** contains the domain controller VM.
-   A dedicated **AVD subnet** contains the Azure Virtual Desktop
    session host.
-   **Azure Virtual Desktop** provides the virtual desktop environment
    to users.
-   Separate profile storage supports persistent user profiles.

![Azure Virtual Desktop Hybrid Identity
Architecture](images/avd-hybrid-identity-architecture.png)

> The diagram above represents the lab architecture used for this
> project. Resource names shown in the diagram are lab-specific.

## Technologies Used

  -----------------------------------------------------------------------
  Area                                Technologies
  ----------------------------------- -----------------------------------
  Cloud Platform                      Microsoft Azure

  Virtual Desktop                     Azure Virtual Desktop (AVD),
                                      Windows 11 multi-session

  Identity                            Active Directory Domain Services
                                      (AD DS), Microsoft Entra ID, AD
                                      Connect Sync

  Image & Application Delivery        Custom Windows image, Sysprep,
                                      Microsoft 365, RemoteApps

  Profile Management                  FSLogix, Azure Files

  Security & Access                   MFA, RBAC, Network Security Groups
                                      (NSGs)

  Networking                          Azure Virtual Network, dedicated DC
                                      and AVD subnets
  -----------------------------------------------------------------------

## Implementation

### 1. Hybrid Identity

-   Deployed an Azure-hosted Active Directory Domain Services
    environment.
-   Connected AD DS identities to Microsoft Entra ID using AD Connect
    Sync.
-   Used the hybrid identity environment to support access to the AVD
    deployment.

### 2. Network Segmentation

The lab uses a dedicated Azure virtual network with separate network
segments for core infrastructure and virtual desktops.

-   **Virtual Network:** `192.168.17.0/24`
-   **DC Subnet:** `192.168.17.0/27`
-   **AVD Subnet:** `192.168.17.128/25`

This separates the domain controller and AVD session-host resources
while keeping them within the same virtual network.

### 3. Azure Virtual Desktop

-   Created an Azure Virtual Desktop environment with a Windows 11
    multi-session host.
-   Built a custom Microsoft 365 Windows image and prepared it using
    Sysprep.
-   Configured virtual desktop and RemoteApp delivery for the simulated
    enterprise environment.

### 4. Persistent User Profiles

-   Implemented FSLogix profile management.
-   Used Azure Files for profile storage.
-   Configured profile persistence so user profile data could remain
    available across AVD sessions.

### 5. Access & Security

The lab incorporated:

-   Multifactor authentication (MFA)
-   Role-based access control (RBAC)
-   Network Security Groups (NSGs)

These controls were used as part of the identity, authorization, and
network-security design of the environment.

## Skills Demonstrated

-   Microsoft Azure administration
-   Azure Virtual Desktop deployment and configuration
-   Windows 11 multi-session administration
-   Active Directory Domain Services
-   Microsoft Entra ID
-   Hybrid identity and directory synchronization
-   Azure virtual networking and subnetting
-   RemoteApp and virtual desktop delivery
-   Windows image preparation with Sysprep
-   FSLogix profile management
-   Azure Files
-   MFA and RBAC
-   Network Security Groups

## Repository Structure

``` text
Azure-Virtual-Desktop-Hybrid-Identity/
│
├── README.md
│
└── images/
    └── avd-hybrid-identity-architecture.png
```

## Project Context

This repository documents a **hands-on lab environment** created to
demonstrate practical Azure, identity, networking, and virtualization
skills. It is not presented as a production enterprise deployment.

The project is relevant to roles such as:

-   IT Support Specialist
-   Service Desk / Desktop Support
-   Junior Systems Administrator
-   Microsoft 365 / Identity Support
-   Junior Azure Administrator

## Security Note

Screenshots and documentation published in this repository should not
expose credentials, passwords, access keys, connection strings,
subscription IDs, sensitive tenant information, or other confidential
data.

## Future Enhancements

Potential additions to this repository include:

-   Sanitized Azure portal screenshots
-   AVD host-pool and session-host configuration evidence
-   FSLogix and Azure Files configuration screenshots
-   Identity synchronization validation
-   Troubleshooting scenarios and resolutions
-   Azure Monitor / Log Analytics integration

------------------------------------------------------------------------

**Author:** Aujas Rajput\
**LinkedIn:**
[linkedin.com/in/aujaswani-rajput](https://www.linkedin.com/in/aujaswani-rajput/)
