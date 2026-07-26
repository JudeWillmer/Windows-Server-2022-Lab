# Shared Folders

## Overview

This section covers the core **Shared Folder** administration tasks I completed within the **Windows Server 2022** lab. I created shared folders and configured both **Share Permissions** and **NTFS Permissions** using **Security Groups** to control user access. These tasks demonstrate how **Windows Server** provides secure, centralised access to shared resources while following common **Active Directory** administration practices.

---

# Task 1 - Creating an SMB Share

## Objective

Create an **SMB Share** for the **JayTech** directory to provide a central location for shared company resources within the **Windows Server 2022** environment.

---

## Implementation

Using the **New Share Wizard** in **Server Manager**, I selected **SMB Share - Advanced**, specified a custom path, and created a new folder named **JayTech** on the **C:** drive. I then selected the **Group Files** folder management property and completed the share creation.

---

## Navigation

```text
Server Manager
→ File and Storage Services
→ Shares
→ New Share
→ SMB Share - Advanced
→ Type a custom path
→ Browse
→ Local Disk (C:)
→ New Folder
→ Create "JayTech"
→ Select Folder
→ Next
→ Group Files
→ Create
```

---

## Outcome

An **SMB Share** was successfully created for the **JayTech** directory, providing a central location that will be used to store and manage shared departmental resources.

---

## Screenshot

**Figure 1:** Creating the **JayTech** folder during the **SMB Share** creation wizard.

<img width="1068" height="913" alt="01 – Creating an SMB Share" src="https://github.com/user-attachments/assets/541e0639-d200-4123-aa78-b8b343be8793" />
