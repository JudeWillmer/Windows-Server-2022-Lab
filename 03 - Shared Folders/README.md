# Shared Folders

## Overview

This section covers the core **Shared Folder** administration tasks I completed within the **Windows Server 2022** lab. I created **SMB shares**, organised departmental folders, and configured both **Share Permissions** and **NTFS Permissions** using **Active Directory Security Groups** to control user access. These tasks demonstrate how **Windows Server** provides secure, centralised access to shared resources while following common **Active Directory** administration practices.

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

<img width="1068" height="892" alt="01 – Creating an SMB Share" src="https://github.com/user-attachments/assets/99140993-7142-47c7-aa2f-d1220681660f" />

# Task 2 - Creating Department Folders

## Objective

Create a structured folder hierarchy within the **JayTech** shared directory to organise departmental resources.

---

## Implementation

Using **File Explorer**, I created separate folders for the **HR**, **IT**, and **Sales** departments within the **JayTech** shared directory. These folders will later be configured with appropriate permissions using **Active Directory Security Groups**.

---

## Navigation

```text
File Explorer
→ Local Disk (C:)
→ JayTech
→ Right-click
→ New
→ Folder
→ Create "HR"
→ Create "IT"
→ Create "Sales"
```

---

## Outcome

Departmental folders were successfully created within the **JayTech** shared directory, providing a structured location for departmental resources that can be secured with appropriate permissions.

---

## Screenshot

**Figure 2:** Department folders created within the **JayTech** shared directory.

<img width="1225" height="915" alt="02 – Creating Department Folders" src="https://github.com/user-attachments/assets/57ada887-45b2-4408-aa53-156cd9f32352" />

# Task 3 - Configuring NTFS Permissions

## Objective

Configure **NTFS Permissions** to restrict access to the **Sales** department folder, ensuring only authorised **Active Directory Security Groups** can access and modify its contents.

---

## Implementation

Using the **Security** properties for the **Sales** folder, I disabled permission inheritance and converted the inherited permissions into explicit permissions. I then removed unnecessary entries and assigned the **Sales_Users** security group with **Modify** permissions, while retaining the default administrative accounts required for system management.

---

## Navigation

```text
File Explorer
→ Local Disk (C:)
→ JayTech
→ Sales
→ Right-click
→ Properties
→ Security
→ Advanced
→ Disable inheritance
→ Convert inherited permissions into explicit permissions
→ Remove unnecessary entries
→ Add "Sales_Users"
→ Allow "Modify"
→ Apply
→ OK
```

---

## Outcome

The **Sales** folder was secured using **NTFS Permissions**, ensuring that only members of the **Sales_Users** security group can modify the folder and its contents while preserving administrative access.

---

## Screenshot

**Figure 3:** Configuring **NTFS Permissions** for the **Sales** department folder.

<img width="1493" height="916" alt="03 – Configuring NTFS Permissions" src="https://github.com/user-attachments/assets/9a61aee0-d337-46bd-87be-8e1128386e34" />

# Task 4 - Configuring Share Permissions

## Objective

Configure **Share Permissions** for the **Sales** shared folder to control how authorised users can access shared resources over the network.

---

## Implementation

Using the **Sharing** properties for the **Sales** folder, I configured **Share Permissions** by adding the **Sales_Users** security group and assigning **Read/Write** access. This allows authorised users to access and modify shared files over the network while maintaining administrative access.

---

## Navigation

```text
File Explorer
→ Local Disk (C:)
→ JayTech
→ Sales
→ Right-click
→ Properties
→ Sharing
→ Share
→ Add "Sales_Users"
→ Set Permission Level to "Read/Write"
→ Share
```

---

## Outcome

The **Sales** shared folder was configured with **Share Permissions**, allowing members of the **Sales_Users** security group to read and modify files when accessing the folder over the network.

---

## Screenshot

**Figure 4:** Configuring **Share Permissions** for the **Sales** shared folder.

<img width="1367" height="916" alt="04 – Configuring Share Permissions" src="https://github.com/user-attachments/assets/e8b51b1c-2a0c-4b57-86b9-26d59eb8f862" />
