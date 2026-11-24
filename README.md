# Project 10: Internal DNS Setup

## Objective
Configured an internal DNS server on Windows Server to access an IIS-hosted web application using a custom hostname instead of directly using its IP address.

## Environment
- **Operating System:** Windows Server 2022
- **DNS Server:** AZ-LKM-JAV-01
- **DNS Server IP:** 10.5.3.141
- **DNS Zone:** `amish.local`
- **Web Server:** IIS (Internet Information Services)
- **Application Hostname:** `app.amish.local`

## Implementation

### 1. DNS Server Configuration
- Opened DNS Manager on Windows Server.
- Accessed the existing Forward Lookup Zone: `amish.local`.
- Verified the DNS zone and its existing DNS records.
- Confirmed the DNS server configuration.

### 2. IIS Installation and Verification
- Installed the Web Server (IIS) role using Server Manager.
- Verified the IIS installation by accessing `http://localhost`.
- Confirmed that the default IIS Welcome page loaded successfully.

### 3. DNS A Record Creation

Created a Host (A) record in the `amish.local` Forward Lookup Zone.

| Property | Value |
|---|---|
| Record Name | app |
| Fully Qualified Domain Name | app.amish.local |
| Record Type | Host (A) |
| IP Address | 10.5.3.141 |

The A record maps the application hostname to the Windows Server IP address.

### 4. Hostname Verification

Accessed the IIS-hosted application using:

`http://app.amish.local`

The IIS Welcome page loaded successfully, confirming that the application was accessible through its custom hostname.

### 5. DNS Lookup Verification

Executed the following command in Command Prompt:

```cmd
nslookup app.amish.local
```

**Expected DNS Resolution:**

```text
Name:    app.amish.local
Address: 10.5.3.141
```

The hostname successfully resolved to the Windows Server IP address, confirming internal DNS resolution.

## Outcome

Successfully configured an internal DNS environment using Windows Server DNS and IIS.

- Created and verified the `amish.local` Forward Lookup Zone.
- Configured an A record for `app.amish.local`.
- Mapped the hostname to `10.5.3.141`.
- Successfully accessed the IIS Welcome page using the custom hostname.
- Verified DNS resolution using `nslookup`.

## Evidence

Screenshots are available in the `screenshots/` directory.

The evidence includes:
1. DNS Manager showing the `amish.local` Forward Lookup Zone.
2. A record configuration for `app`.
3. IIS Welcome page accessed through `app.amish.local`.
4. Command Prompt showing successful `nslookup` resolution.

## Technologies Used
- Windows Server 2022
- DNS Server
- DNS Manager
- Internet Information Services (IIS)
- Command Prompt
- `nslookup`
