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
