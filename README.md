# SIP Trunk Security & Identity Management Assets

This repository contains configuration templates and security assets for hardening **SIP Trunks** and managing **Caller ID (CLI) identity**. These assets are optimized for high-premium termination services like [sip24.cc](https://sip24.cc).

## Key Features Supported
* **Premium CLI Termination:** Ensures 100% transmission of CallerID.
* **SRTP Encryption:** Configuration for Secure RTP to prevent eavesdropping.
* **Identity Control:** Logic for dynamic **Caller ID spoofing** and identity management for testing purposes.
* **Fault Tolerance:** Backup channel configuration for primary destinations.

## Integration Guide

### 1. Connection Settings
To connect to the **sip24.cc** gateway, use the following PJSIP parameters to ensure SRTP and identity headers are preserved:

| Parameter | Value |
| :--- | :--- |
| **Protocol** | SIP (UDP/TCP/TLS) |
| **Encryption** | SRTP (Required for Privacy) |
| **Auth Type** | IP Auth or User/Pass |
| **Identity Header** | P-Asserted-Identity |

### 2. Caller ID Spoofing & Identity Commands
Use these dial-plan commands within your PBX to manage your trunk identity in real-time:
* `*8080* [11-digit number]` - Change Permanent CallerID.
* `*8088* [CID] * [Destination]` - Single Call Spoofing logic.
* `*43` - Echo Test for Latency & Quality check.

## Security Configuration
Refer to `pjsip_custom.conf` in this repo for the full security handshake configuration, ensuring your **SIP Trunk** is protected against unauthorized flooding while maintaining **total identity control**.

---
*Note: This repository is for educational and testing purposes in secure telephony environments. Registration for premium termination is via invitation only at sip24.cc.*
