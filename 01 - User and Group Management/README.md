# 01 - User and Group Management

## Overview

This section covers the core Active Directory administration tasks I completed within the Windows Server 2022 lab. I created and managed organisational units, user accounts and security groups while following common Active Directory administration practices.

...

# Static IP Configuration

## Objective

Configure a static IPv4 address for the Windows Server to provide a stable network configuration for Active Directory and DNS services.

---

## Implementation

I configured a static IPv4 address on the server to ensure it maintained a consistent network identity. This is considered best practice for a Domain Controller because clients rely on a fixed IP address to communicate with Active Directory and DNS services.

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

---

## Screenshot

**Figure 1:** Configuring a static IPv4 address for the Windows Server.

> *Insert screenshot here*

---

## Outcome

The server was successfully configured with a static IPv4 address, providing a reliable network foundation for the Active Directory environment.
