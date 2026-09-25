# Personal Device Hardening Checklist

## Goal

Apply concrete hardening steps to my personal laptop to enhance operating system, network, account, and physical security in accordance with Cisco cybersecurity standards.

## Steps

1. Assessed the baseline configuration across operating system, authentication, storage, network, software, account, and physical security parameters.
2. Implemented required hardening controls including full-disk encryption, firewall configuration, account privilege separation, and application cleanup.
3. Verified and documented the post-hardening system state.

---

## Findings & System Audit

### Checklist Audit & Verification

| Category | Hardening Item | Baseline State | Applied Change / Action Taken | Verified Final State |
| --- | --- | --- | --- | --- |
| **Operating System** | OS Support & Security Updates | Windows 11 Home / Fully supported | Ran `ms-settings:windowsupdate` to check for pending definition patches. | OS fully updated to latest build. |
|  | Automatic Updates | Active by default | Confirmed automatic update settings are set to download without delay. | Automatic updates enabled. |
|  | Pending Updates | 1 cumulative update pending | Restarted system to complete patch installation. | Zero pending updates. |
| **Authentication** | Login Password / PIN | PIN enabled | Ensured complex Alphanumeric PIN requirement is enforced. | Complex PIN active. |
|  | Screen Lock Timeout | Set to 15 minutes | Changed automatic lock timeout under Power & Sleep settings to 3 minutes. | Screen locks after 3 mins inactivity. |
|  | Biometrics Layer | Windows Hello Fingerprint configured | Retained fingerprint sign-in with complex PIN fallback. | Multi-factor local auth ready. |
| **Storage & Data** | Full-Disk Encryption | Device Encryption (BitLocker) | Confirmed BitLocker / Device Encryption is active on primary drive C:. | Full-disk encryption active. |
|  | Backup Status | OneDrive + External drive | Created fresh system image and critical folder backup to external drive. | Off-site / offline backup complete. |
|  | Backup Recovery Test | Not tested recently | Restored a test document from external backup to verify file integrity. | Recovery test successful. |
| **Network** | Host Firewall | Microsoft Defender Firewall active | Verified rules; blocked incoming unsolicited requests across profiles. | Host firewall active. |
|  | Network Profile | Set to Private | Switched primary active connection profile to "Public" for strict filtering. | Profile set to Public. |
|  | Unnecessary Sharing Services | Network Discovery enabled | Disabled SMB file sharing and Network Discovery on public interfaces. | Unnecessary shares disabled. |
| **Software** | Browser Version | Chrome / Edge installed | Updated browser to latest release version. | Browsers up to date. |
|  | Anti-Malware Solution | Windows Defender active | Executed full system scan; confirmed real-time protection is running. | Real-time protection active. |
| **Software Cleanup** | Removed Unused Apps | Unnecessary bloatware present | Uninstalled 3 unused apps: *Cortana*, *Candy Crush Soda Saga*, *Xbox Live Speech Window*. | Storage freed, attack surface reduced. |
| **Accounts** | Account Privilege Separation | Single admin account used daily | Created standard User account for daily work; reserved Admin rights for elevated tasks. | Daily account is Non-Admin. |
|  | Guest Account | Disabled | Confirmed local Guest account status via `net user`. | Guest account disabled. |
| **Physical Security** | Travel Storage & Find My Device | Find My Device active | Verified "Find My Device" GPS tracking is turned ON in settings. | Tracking active. |
|  | Remote Wipe Capability | Account linked | Tested Microsoft Account portal remote lock/wipe capabilities. | Remote wipe verified. |

---

### Reflection & Key Security Takeaways

Executing this device hardening process highlighted that default operating system settings often prioritize convenience over maximum security. Reducing the screen lock timeout to three minutes and switching the active network profile to Public immediately closed obvious physical and local network exposure windows.

The most impact came from creating a dedicated Standard User account for daily tasks instead of operating under an Administrator account permanently. This prevents unauthorized scripts or malicious executables from making system-wide changes without explicit credential confirmation, providing a vital layer of defense against drive-by downloads and malware propagation.
