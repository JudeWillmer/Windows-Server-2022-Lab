# User and Group Management

## Overview

This section covers the core **Active Directory** administration tasks I completed within the **Windows Server 2022** lab. I created and managed **Organisational Units (OUs)**, **user accounts**, and **security groups** while following common Active Directory administration practices.

---

# Task 1 - Static IP Configuration

## Objective

Configure a **static IPv4 address** for the Windows Server to provide a stable network configuration for **Active Directory** and **DNS** services.

---

## Implementation

I configured a **static IPv4 address** on the server to ensure it maintained a consistent network identity. This is considered best practice for a **Domain Controller** because clients rely on a fixed IP address to communicate with **Active Directory** and **DNS** services.

---

## Navigation

```text
Control Panel
→ Network and Internet
→ Network Connections
→ Right-click Ethernet
→ Properties
→ Internet Protocol Version 4 (TCP/IPv4)
→ Properties
→ Configure Static IP Address
→ OK
```

## Outcome
The server was successfully configured with a static IPv4 address, providing a reliable network foundation for the Active Directory environment.

---

## Screenshot

**Figure 1:** Configuring a static IPv4 address for the Windows Server.

<img width="1273" height="883" alt="01 – Static IP Configuration" src="https://github.com/user-attachments/assets/c909e1c9-e5c9-49ac-9d34-42d8f5d3df63" />

# Task 2 - Creating the Organisational Unit (OU) Structure

## Objective

Create a structured **Organisational Unit (OU)** hierarchy within **Active Directory** to organise users, computers, and security groups for the fictional **JayTech** environment.

---

## Implementation

I created a structured **Organisational Unit (OU)** hierarchy within the **JayTech** organisational unit to organise users, computers, and security groups into logical containers. This structure simplifies administration, supports the application of **Group Policy**, and follows common **Active Directory** best practices.

---

## Navigation

```text
Active Directory Users and Computers
→ Expand lab.local
→ Right-click JayTech
→ New
→ Organisational Unit
→ Enter OU Name
→ OK
```

*Repeat the process for each Organisational Unit created.*

---

## Outcome

A structured **Active Directory** environment was created within the **JayTech** organisational unit, providing a logical hierarchy for managing users, computers, and security groups throughout the Windows Server lab.

---

## Screenshot

**Figure 2:** Organisational Unit structure created within the **JayTech** organisational unit.

<img width="1917" height="892" alt="02 – Creating the Organisational Unit (OU) Structure" src="https://github.com/user-attachments/assets/9060cdf1-f49f-41b6-8924-c509094e04fb" />
