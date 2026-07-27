# Domain Join

## Overview

This section covers the core **Active Directory** domain administration tasks I completed within the **Windows Server 2022** lab. I joined a **Windows** client computer to the **lab.local** domain, verified successful authentication using a domain user account, and accessed shared network resources using **Active Directory Security Groups**. These tasks demonstrate how domain-joined computers provide centralised authentication and secure access to shared resources within a **Windows Server** environment.

---

# Task 1 - Joining a Windows 10 Client to the Domain

## Objective

Join a Windows 10 client to the **lab.local** Active Directory domain by renaming the computer, joining it to the domain, and verifying that the computer account is successfully created in Active Directory.

---

## Implementation

1. Open **This PC** and select **Properties**.
2. Select **Rename this PC (Advanced)**.
3. Rename the computer to **CLIENT01** and restart the device.
4. Open **System Properties**, select **Change**, then choose **Domain**.
5. Enter **lab.local** as the domain name.
6. Authenticate using a Domain Administrator account when prompted.
7. Restart the computer to complete the domain join.
8. Open **Active Directory Users and Computers** and verify that **CLIENT01** appears in the **Computers** container.

---

## Navigation

```text
This PC
→ Properties
→ Rename this PC (Advanced)
→ Change
→ Domain
→ Enter "lab.local"
→ Restart
```

---

## Outcome

The Windows 10 client was successfully joined to the **lab.local** Active Directory domain. After restarting, the computer account appeared in **Active Directory Users and Computers**, confirming the domain join was successful.

---

## Screenshot

**Figure 1:** **CLIENT01** successfully joined to the **lab.local** domain and displayed in the **Computers** container within **Active Directory Users and Computers**.

<img width="1212" height="892" alt="01 – Joining a Windows 10 Client to the Domain" src="https://github.com/user-attachments/assets/419c36c1-4626-4964-9f4f-05115baf5e76" />

# Task 2 - Signing in with a Domain User Account

## Objective

Sign in to the Windows 10 client using a domain user account and verify that the configured Group Policy password and account lockout policies have been successfully applied.

---

## Implementation

1. Sign out of the local Windows account.
2. Sign in using the **LAB\MarioKatoch** domain account.
3. Open **Command Prompt**.
4. Run the following command:

```cmd
net accounts
```

5. Review the output to verify that the configured password and account lockout policies have been applied.

---

## Navigation

```text
Start
→ User Account
→ Sign out

Sign in
→ LAB\MarioKatoch

Start
→ Command Prompt
→ net accounts
```

---

## Outcome

The Windows 10 client successfully authenticated using the **LAB\MarioKatoch** domain account. The `net accounts` command confirmed that the Group Policy password and account lockout settings configured earlier in the lab were successfully applied.

---

## Screenshot

**Figure 2:** Output of the `net accounts` command confirming that the Group Policy password and account lockout settings were successfully applied to the Windows 10 client.

<img width="1568" height="890" alt="02 – Signing in with a Domain User Account" src="https://github.com/user-attachments/assets/6bc431fa-af8e-447c-97a1-aa70e5e88606" />
