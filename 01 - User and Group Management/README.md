# User and Group Management

## Overview

This section covers the core **Active Directory** administration tasks I completed within the **Windows Server 2022** lab. I created and managed **Organisational Units (OUs)**, **user accounts**, and **security groups**, while performing common administrative tasks such as assigning users to groups, resetting passwords, and disabling user accounts. These tasks demonstrate the fundamental account and identity management skills used in a typical **Windows Server** environment.

---

# Task 1 - Configuring a Static IPv4 Address

## Objective

Configure a **static IPv4 address** on the **Windows Server 2022** Domain Controller to provide a stable network configuration for **Active Directory** and **DNS** services.

---

## Implementation

I configured a **static IPv4 address** on the server's **internal network adapter** to ensure the **Domain Controller** maintained a consistent network identity. A static IP address is considered best practice because **Active Directory** and **DNS** services rely on a fixed address so that domain-joined devices can reliably locate and communicate with the server.

---

## Navigation

```text
Control Panel
→ Network and Internet
→ Network Connections
→ Right-click Ethernet 2
→ Properties
→ Internet Protocol Version 4 (TCP/IPv4)
→ Properties
→ Configure Static IPv4 Address
→ OK
```

---

## Outcome

The **internal network adapter** was successfully configured with a **static IPv4 address**, providing a stable network foundation for **Active Directory**, **DNS**, and future domain-joined client computers.

---

## Screenshot

**Figure 1:** Configuring a **static IPv4 address** on the **internal network adapter** for the **Windows Server 2022** Domain Controller.

<img width="1285" height="871" alt="01 – Static IP Configuration" src="https://github.com/user-attachments/assets/ee4a265c-9e73-4b9a-a21e-8c55af498626" />

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

*Repeated the process for each Organisational Unit created.*

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

# Task 6 - Resetting a User Password

## Objective

Reset an **Active Directory** user account password to restore account access and maintain secure user account administration.

---

## Implementation

I reset the password for an existing **Active Directory** user account using **Active Directory Users and Computers**. Password resets are one of the most common tasks performed by **IT Support** and **System Administrators**, allowing users to regain access to their accounts while supporting secure authentication and organisational security policies.

---

## Navigation

```text
Active Directory Users and Computers
→ Expand lab.local
→ Expand JayTech
→ Expand Users
→ Right-click User
→ Reset Password
→ Enter New Password
→ Confirm New Password
→ Configure Password Options
→ OK
```

---

## Outcome

The user's password was successfully reset, allowing them to authenticate using the new credentials. Password reset options, such as requiring the user to change their password at the next sign-in, help maintain security and encourage users to create their own confidential passwords.

---

## Screenshot

**Figure 6:** Resetting an **Active Directory** user account password within the **JayTech** environment.

<img width="1137" height="887" alt="06 – Resetting a User Password" src="https://github.com/user-attachments/assets/c157f0d0-bb36-495f-b03e-33c1c9ee35f7" />

# Task 7 - Disabling a User Account

## Objective

Disable an **Active Directory** user account to prevent access while retaining the account and its associated data for future administration if required.

---

## Implementation

I disabled an existing **Active Directory** user account using **Active Directory Users and Computers**. Disabling an account is a common administrative task performed when an employee leaves an organisation, takes an extended period of leave, or when temporary access needs to be suspended without permanently deleting the account.

---

## Navigation

```text
Active Directory Users and Computers
→ Expand lab.local
→ Expand JayTech
→ Expand Users
→ Right-click User
→ Disable Account
→ OK
```

---

## Outcome

The selected user account was successfully disabled, preventing the user from authenticating to the domain while preserving the account, group memberships, and associated information for future use if required.

---

## Screenshot

**Figure 7:** Disabled **Active Directory** user account within the **JayTech** environment.

<img width="1113" height="891" alt="07 – Disabling a User Account" src="https://github.com/user-attachments/assets/32beeae2-a124-4026-bd2d-5aef825f36d1" />
