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

# Task 3 - Creating a User Account

## Objective

Create a **user account** within the **Active Directory** environment to represent an employee in the fictional **JayTech** organisation.

---

## Implementation

I created a new **Active Directory** user account within the appropriate **Organisational Unit (OU)**. User accounts allow employees to authenticate to the domain, access network resources, and receive permissions based on their assigned security groups.

---

## Navigation

```text
Active Directory Users and Computers
→ Expand lab.local
→ Expand JayTech
→ Right-click Users
→ New
→ User
→ Enter User Details
→ Next
→ Configure Password
→ Next
→ Finish
```

---

## Outcome

A new **Active Directory** user account was successfully created within the **JayTech** environment and is ready to be assigned to security groups and granted access to network resources.

---

## Screenshot

**Figure 3:** Creating a new user account within the **JayTech** Active Directory environment.

<img width="1917" height="888" alt="03 – Creating a User Account" src="https://github.com/user-attachments/assets/35dbc75f-0684-48ae-98d1-b1243b33a658" />

# Task 4 - Creating a Security Group

## Objective

Create a **security group** within **Active Directory** to simplify permission management and provide a scalable way to assign access to users.

---

## Implementation

I created a new **security group** within the **Groups** organisational unit. Security groups allow permissions to be assigned to a group rather than individual users, making administration more efficient and easier to manage as the environment grows.

---

## Navigation

```text
Active Directory Users and Computers
→ Expand lab.local
→ Expand JayTech
→ Right-click Groups
→ New
→ Group
→ Enter Group Name
→ Select Global
→ Select Security
→ OK
```

---

## Outcome

A **Global Security Group** was successfully created within the **JayTech** environment. The group can now be used to manage permissions and simplify user administration throughout the Active Directory environment.

---

## Screenshot

**Figure 4:** Creating a Global Security Group within the **JayTech** Active Directory environment.

<img width="1087" height="888" alt="04 – Creating a Security Group" src="https://github.com/user-attachments/assets/7e4fdf91-ef56-4213-99dc-92a12289a18c" />

# Task 5 - Managing Security Group Membership<img width="1138" height="892" alt="05 – Managing Security Group Membership" src="https://github.com/user-attachments/assets/465fdbfe-5dbf-4a98-a603-99579063065e" />


## Objective

Assign **Active Directory** user accounts to **security groups** to simplify permission management and prepare the environment for assigning access to network resources.

---

## Implementation

I added users to their appropriate **security groups** based on their department and role within the fictional **JayTech** organisation. Assigning users to security groups allows permissions to be managed centrally, making it easier to grant or revoke access without configuring permissions for individual user accounts.

---

## Navigation

```text
Active Directory Users and Computers
→ Expand lab.local
→ Expand JayTech
→ Expand Groups
→ Right-click Security Group
→ Properties
→ Members
→ Add
→ Enter User Name
→ Check Names
→ OK
→ Apply
→ OK
```

---

## Outcome

The selected users were successfully assigned to their respective **security groups**, providing a scalable and efficient way to manage permissions throughout the **Active Directory** environment.

---

## Screenshot

**Figure 5:** Users assigned to the appropriate security groups within the **JayTech** Active Directory environment.

<img width="1138" height="892" alt="05 – Managing Security Group Membership" src="https://github.com/user-attachments/assets/5eada875-1c9a-4ea2-8eb9-352614b3d4f5" />
