# Troubleshooting

## Overview

This section covers the common troubleshooting tasks I completed within the **Windows Server 2022** lab. I diagnosed and resolved common **Active Directory**, **Group Policy**, **Shared Folder**, and **DNS** issues using built-in **Windows** administrative tools and command-line utilities. These tasks demonstrate practical troubleshooting techniques used to identify, investigate, and resolve common issues within a **Windows Server** environment.

---

# Task 1 - Unlocking a Locked Domain Account

## Objective

Simulate an **Active Directory** account lockout by entering an incorrect password multiple times, then restore access by unlocking the **domain user account** in **Active Directory Users and Computers**.

---

## Implementation

I entered an incorrect password multiple times while signing in as **LAB\katoch.m**, causing the configured **Account Lockout Policy** to lock the domain user account. I then opened **Active Directory Users and Computers**, located the **Mario Katoch** user account, and unlocked it from the **Account** tab within the user properties. After applying the changes, I signed in using the correct password and verified the successful domain authentication using the `whoami` command.

---

## Navigation

```text
Server Manager
→ Tools
→ Active Directory Users and Computers
→ lab.local
→ Users
→ Mario Katoch
→ Properties
→ Account
→ Unlock account
→ Apply
→ OK
```

---

## Outcome

The locked **Active Directory** user account was successfully unlocked, restoring access to the **lab.local** domain. Successful authentication was verified by signing in with the **LAB\katoch.m** domain account and confirming the logged-in user using the `whoami` command.

---

## Scenario

A user contacts the IT Help Desk after being unable to sign in to their **domain account**. The account was automatically locked after multiple incorrect password attempts triggered the configured **Account Lockout Policy**. I investigated the issue by opening **Active Directory Users and Computers**, locating the affected user account, and confirming that the account was locked. I restored access by unlocking the account and then verified that the user could successfully authenticate to the **lab.local** domain using the correct credentials.

Account lockouts are one of the most common support requests within **Active Directory** environments. Understanding how to identify, resolve, and verify these issues enables IT Support professionals to restore user access quickly while maintaining the security controls enforced through **Group Policy**.

---

## Screenshot

**Figure 1:** Domain user account locked after multiple incorrect password attempts.

<img width="1917" height="952" alt="01 – Unlocking a Locked Domain Account" src="https://github.com/user-attachments/assets/e21d9148-69ef-476a-8797-11c9a8adde2f" />

**Figure 2:** Unlocking the locked domain user account in **Active Directory Users and Computers**.

<img width="1420" height="888" alt="02 – Unlocking a Locked Domain Account" src="https://github.com/user-attachments/assets/ee252108-8d3d-4f02-8e63-b1c0d44dcf08" />

**Figure 3:** Successful domain sign-in verified using the `whoami` command.

<img width="1231" height="911" alt="03 – Unlocking a Locked Domain Account" src="https://github.com/user-attachments/assets/3dbb9c8d-f800-4ca4-8411-2b37c5dee75a" />

# Task 2 - Re-enabling a Disabled Domain User Account and Resetting the Password

## Objective

Restore access to a disabled **Active Directory** user account by re-enabling the account, resetting the password, and requiring the user to create a new password at the next sign-in.

---

## Implementation

I disabled the **Mario Katoch** domain user account in **Active Directory Users and Computers** to simulate a common account access issue. I then re-enabled the account, reset the user's password, and selected **User must change password at next logon** to enforce a secure password update. During the first sign-in, I attempted to create a password that did not meet the configured **Password Policy** requirements before successfully creating a compliant password. Finally, I verified successful authentication to the **lab.local** domain using the `whoami` command.

---

## Navigation

```text
Server Manager
→ Tools
→ Active Directory Users and Computers
→ lab.local
→ Users
→ Mario Katoch
→ Right-click
→ Enable Account

Right-click
→ Reset Password
→ User must change password at next logon
→ OK
```

---

## Outcome

The disabled **Active Directory** user account was successfully re-enabled and secured with a new password. The configured **Password Policy** correctly rejected a non-compliant password before allowing a compliant password to be created. Successful authentication to the **lab.local** domain was verified using the `whoami` command.

---

## Scenario

A user contacts the IT Help Desk after being unable to sign in to their **domain account** because it has been disabled. I investigated the issue using **Active Directory Users and Computers**, confirmed that the account was disabled, and restored access by re-enabling the account before resetting the user's password. To improve account security, I required the user to create a new password during the next sign-in. When a password that did not meet the configured **Password Policy** requirements was entered, the change was rejected until a compliant password was created. I then verified that the user could successfully authenticate to the **lab.local** domain.

Disabled user accounts are commonly encountered within **Active Directory** environments due to administrative actions, security procedures, or account management requirements. Understanding how to safely restore user access while enforcing secure password practices is an essential responsibility for **IT Support** and **Help Desk** professionals.

---

## Screenshot

**Figure 1:** Domain user account disabled, preventing successful authentication.

<img width="1918" height="952" alt="04 – Re-enabling a Disabled Domain User Account and Resetting the Password" src="https://github.com/user-attachments/assets/961498af-a6b1-43a4-a177-d619d6593188" />

**Figure 2:** Re-enabling the disabled domain user account in **Active Directory Users and Computers**.

<img width="1607" height="891" alt="05 – Re-enabling a Disabled Domain User Account and Resetting the Password" src="https://github.com/user-attachments/assets/020ade38-4f25-4c33-8d38-afe45d29c8d2" />

**Figure 3:** Resetting the domain user password and requiring a password change at the next sign-in.

<img width="1312" height="890" alt="06 – Re-enabling a Disabled Domain User Account and Resetting the Password" src="https://github.com/user-attachments/assets/d3e6cb0e-a94a-4dba-b8b2-50c321aa5e77" />

**Figure 4:** Password rejected because it does not meet the configured **Password Policy** requirements.

<img width="1918" height="952" alt="07 – Re-enabling a Disabled Domain User Account and Resetting the Password" src="https://github.com/user-attachments/assets/90aee84b-03a3-4fdb-9a96-946826694f1a" />

**Figure 5:** Successful domain authentication verified using the `whoami` command after creating a compliant password.

<img width="1231" height="911" alt="08 – Re-enabling a Disabled Domain User Account and Resetting the Password" src="https://github.com/user-attachments/assets/d3841f22-4945-4640-a554-21591948a3c4" />

# Task 3 - Extending an Expired User Account

## Objective

Restore access to an **Active Directory** user account by extending the account expiry date and verifying successful authentication to the **lab.local** domain.

---

## Implementation

I configured the **Mario Katoch** domain user account to expire in **Active Directory Users and Computers** to simulate a common account access issue. I then extended the account expiry date from the **Account** tab within the user properties before applying the changes. After updating the account, I signed in using the **LAB\katoch.m** domain account and verified successful authentication using the `whoami` command.

---

## Navigation

```text
Server Manager
→ Tools
→ Active Directory Users and Computers
→ lab.local
→ Users
→ Mario Katoch
→ Properties
→ Account
→ Account expires
→ Select a new expiry date
→ Apply
→ OK
```

---

## Outcome

The expired **Active Directory** user account was successfully reactivated by extending the account expiry date. Successful authentication to the **lab.local** domain was verified using the `whoami` command.

---

## Scenario

A user contacts the IT Help Desk after being unable to sign in to their **domain account** because the account has expired. I investigated the issue using **Active Directory Users and Computers**, confirmed that the account had reached its configured expiry date, and restored access by extending the account expiry date. After applying the changes, I verified that the user could successfully authenticate to the **lab.local** domain using the correct credentials.

Expired user accounts are commonly encountered within **Active Directory** environments where temporary staff, contractors, or time-limited accounts are used. Understanding how to identify expired accounts and safely restore user access is an important responsibility for **IT Support** and **Help Desk** professionals while maintaining effective account lifecycle management.

---

## Screenshot

**Figure 1:** Expired domain user account preventing successful authentication.

<img width="1918" height="952" alt="09 – Extending an Expired User Account" src="https://github.com/user-attachments/assets/7342078f-6083-41a0-bd3b-0a1664db9f5b" />

**Figure 2:** Extending the account expiry date in **Active Directory Users and Computers**.

<img width="1643" height="892" alt="10 – Extending an Expired User Account" src="https://github.com/user-attachments/assets/7ba0bf3d-834f-4ece-8acd-0916401786d0" />

**Figure 3:** Successful domain authentication verified using the `whoami` command after extending the account expiry date.

<img width="1231" height="911" alt="11 – Extending an Expired User Account" src="https://github.com/user-attachments/assets/c6f3e5ca-7995-4db5-b92f-b7bdde3da423" />

# Task 4 - Troubleshooting Group Policy Application

## Objective

Troubleshoot a **Group Policy** setting that is not being applied to a domain user and verify successful policy application using built-in Windows command-line tools.

---

## Implementation

I investigated why the configured desktop wallpaper was not being applied to a domain user after signing in to the **Windows 10** client. I refreshed **Group Policy** using the `gpupdate /force` command and verified the applied **Group Policy Objects** using `gpresult /r`, which confirmed that the expected user policy had not been applied. I then reviewed the **Desktop Wallpaper** policy within the **Default Domain Policy**, corrected the configuration by using a **network-accessible shared folder (UNC path)** for the wallpaper, and applied the changes. After refreshing **Group Policy** and signing back into the client, I verified that the desktop wallpaper was successfully applied.

---

## Navigation

```text
Windows 10 Client
→ Command Prompt
→ gpupdate /force
→ gpresult /r

Server Manager
→ Tools
→ Group Policy Management
→ Forest: lab.local
→ Domains
→ lab.local
→ Default Domain Policy
→ Edit
→ User Configuration
→ Policies
→ Administrative Templates
→ Desktop
→ Desktop
→ Desktop Wallpaper
```

---

## Outcome

The **Desktop Wallpaper Group Policy** was successfully applied after correcting the policy configuration to reference a network-accessible shared folder. Successful policy deployment was verified by refreshing **Group Policy** and confirming that the standard company desktop wallpaper was displayed on the domain client.

---

## Scenario

A user contacts the IT Help Desk because the standard **JayTech** desktop wallpaper is not displayed after signing in to a domain-joined workstation. I investigated the issue by refreshing **Group Policy** on the client and reviewing the applied **Group Policy Objects**, confirming that the expected user policy had not been applied. I then reviewed the **Desktop Wallpaper** policy within **Group Policy Management**, corrected the wallpaper path to reference a network-accessible shared folder on the domain controller, refreshed **Group Policy**, and confirmed that the company wallpaper was successfully applied. This demonstrates a common **Group Policy** troubleshooting process used to investigate and resolve policy deployment issues within an **Active Directory** environment.

---

## Screenshot

**Figure 1:** Standard Windows desktop displayed because the Desktop Wallpaper Group Policy has not been applied.

<img width="1918" height="911" alt="12 – Troubleshooting Group Policy Application" src="https://github.com/user-attachments/assets/bb1f8fcf-8e89-4a0b-98cc-db27fe4e440c" />

**Figure 2:** Refreshing Group Policy on the domain client using the `gpupdate /force` command.

<img width="1423" height="912" alt="13 – Troubleshooting Group Policy Application" src="https://github.com/user-attachments/assets/1aef54f6-d9cc-4f67-a4d1-8d70acc4de9b" />

**Figure 3:** Verifying that the expected user Group Policy had not been applied using the `gpresult /r` command.

<img width="1440" height="912" alt="14 – Troubleshooting Group Policy Application" src="https://github.com/user-attachments/assets/2a9ab24b-e6e5-45f7-bd36-925d3e3ce8b6" />

**Figure 4:** Correcting the Desktop Wallpaper policy within the **Default Domain Policy** by configuring a network-accessible wallpaper location.

<img width="1721" height="892" alt="15 – Troubleshooting Group Policy Application" src="https://github.com/user-attachments/assets/0e42551a-1ae1-462f-8cb1-5b94882db6a5" />

**Figure 5:** Desktop Wallpaper Group Policy successfully applied after correcting the Group Policy configuration and refreshing Group Policy on the domain client.

<img width="1917" height="913" alt="16 – Troubleshooting Group Policy Application" src="https://github.com/user-attachments/assets/75dd680a-2721-4113-ad5c-fcbda769d8fb" />

# Task 5 - Restoring Access to a Shared Folder

## Objective

Troubleshoot and restore access to a shared network folder by identifying and correcting a missing **Active Directory** security group membership.

---

## Implementation

I investigated why a domain user was unable to access the mapped **Sales** shared folder after receiving an **Access Denied** error. I reviewed the user's **Active Directory** group memberships and identified that the required **Sales_Users** security group membership had been removed. I restored the user's membership to the **Sales_Users** security group, signed out of the client workstation, and signed back in to refresh the user's security token. I then verified that access to the shared folder had been successfully restored.

---

## Navigation

```text
Server Manager
→ Tools
→ Active Directory Users and Computers
→ JayTech
→ Users
→ Mario Katoch
→ Properties
→ Member Of
```

---

## Outcome

Access to the **Sales** shared folder was successfully restored by reassigning the appropriate **Active Directory** security group membership. After the user signed back in, the mapped network drive was accessible and normal access to the shared folder was restored.

---

## Scenario

A user contacts the IT Help Desk after receiving an **Access Denied** error when attempting to access the mapped **Sales** shared folder. I investigated the issue by reviewing the user's **Active Directory** group memberships and identified that the required **Sales_Users** security group membership had been removed. After restoring the user's membership and refreshing the user's logon session, I confirmed that access to the shared folder had been successfully restored. This demonstrates how **Active Directory** security groups are commonly used to manage access to shared network resources within a **Windows Server** environment.

---

## Screenshot

**Figure 1:** Reviewing the user's **Active Directory** group memberships and identifying that the **Sales_Users** security group membership is missing.

<img width="1413" height="891" alt="17 – Restoring Access to a Shared Folder" src="https://github.com/user-attachments/assets/71c0fa9a-2077-40f1-ae28-4999e7ead2a9" />

**Figure 2:** Verifying that access to the **Sales** shared folder is denied after the required **Active Directory** security group membership was removed.

<img width="1918" height="913" alt="18 – Restoring Access to a Shared Folder" src="https://github.com/user-attachments/assets/4dbca07a-1d21-4391-837d-4e5fed742938" />

**Figure 3:** Restoring access by adding the user back to the **Sales_Users** Active Directory security group.

<img width="1472" height="913" alt="19 – Restoring Access to a Shared Folder" src="https://github.com/user-attachments/assets/61b7a8b8-9d79-468b-af6e-8e93f1fc35b1" />

**Figure 4:** Verifying that access to the **Sales** shared folder was successfully restored after updating the user's **Active Directory** group membership.

<img width="1631" height="915" alt="20 – Restoring Access to a Shared Folder" src="https://github.com/user-attachments/assets/c442596d-5b26-4db0-9a30-15c0312a3da9" />

# Task 6 - Troubleshooting DNS Resolution

## Objective

Troubleshoot and restore DNS name resolution by identifying and correcting an incorrect DNS server configuration on a domain-joined client.

---

## Implementation

I investigated why a domain-joined client was unable to resolve the domain controller hostname. I confirmed the issue by attempting to ping the domain controller, which failed due to a DNS resolution error. I reviewed the client's IPv4 configuration and identified that the Preferred DNS Server was incorrectly configured to use a public DNS server instead of the internal **Active Directory** DNS server. I corrected the DNS server configuration, cleared the DNS resolver cache, and verified that the client could successfully resolve and communicate with the domain controller.

---

## Navigation

Control Panel  
→ Network and Internet  
→ Network and Sharing Center  
→ Change adapter settings  
→ Ethernet  
→ Properties  
→ Internet Protocol Version 4 (TCP/IPv4)  
→ Properties

---

## Outcome

DNS name resolution was successfully restored by correcting the client's Preferred DNS Server configuration. After clearing the DNS resolver cache, the client successfully resolved the domain controller hostname and normal network communication was restored.

---

## Scenario

A user contacts the IT Help Desk after reporting that they are unable to access domain resources using the server hostname. I investigated the issue by testing connectivity and reviewing the client's network configuration. The workstation was found to be using an incorrect public DNS server instead of the internal **Active Directory** DNS server. After correcting the DNS configuration and clearing the DNS resolver cache, I verified that the client could successfully resolve and communicate with the domain controller.

---

## Screenshot

**Figure 1:** Confirming that the domain controller hostname cannot be resolved after the client was configured to use an incorrect DNS server.

<img width="1495" height="912" alt="21 – Troubleshooting DNS Resolution" src="https://github.com/user-attachments/assets/e55d389d-f11d-48aa-b540-8135612447fd" />

**Figure 2:** Reviewing the client's IPv4 configuration and identifying that the Preferred DNS Server is incorrectly configured to use a public DNS server instead of the internal **Active Directory** DNS server.

<img width="1342" height="915" alt="22 – Troubleshooting DNS Resolution" src="https://github.com/user-attachments/assets/9d2b9aa1-a36b-4de0-bff4-08d23484e988" />

**Figure 3:** Correcting the client's Preferred DNS Server to use the internal **Active Directory** DNS server hosted on the domain controller.

<img width="1388" height="915" alt="23 – Troubleshooting DNS Resolution" src="https://github.com/user-attachments/assets/8a390353-adb9-4255-80ca-2d36fcb61020" />

**Figure 4:** Verifying that DNS resolution was successfully restored by clearing the DNS resolver cache and confirming that the client can successfully resolve and communicate with the domain controller.

<img width="1505" height="912" alt="24 – Troubleshooting DNS Resolution" src="https://github.com/user-attachments/assets/3639752c-94a7-4e37-9f49-6f6008b04592" />
