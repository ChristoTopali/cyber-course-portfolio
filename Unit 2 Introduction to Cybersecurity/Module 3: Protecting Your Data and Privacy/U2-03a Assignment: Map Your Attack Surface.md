# Personal Attack Surface Inventory

## Goal

Develop awareness of my personal digital footprint by inventorying the devices, accounts, and services I use, and evaluate potential security exposures.

## Steps

1. Audited all personal and educational devices, active logins, and security settings.
2. Inventoried major online accounts, evaluating MFA adoption and credential uniqueness.
3. Identified top high-value targets from an attacker's perspective and drafted a personal remediation plan.

---

## Findings

### Devices Inventory

| Device | Logged-in Accounts | Sensitive Data Stored/Accessed | Security Controls |
| --- | --- | --- | --- |
| Personal Laptop | Google, GitHub, Microsoft 365, Discord | School projects, local source code, stored browser sessions | Up-to-date OS, PIN & Biometric lock enabled |
| Smartphone | Google, Banking apps, Social Media, Email | Mobile banking access, 2FA authenticator codes, personal photos, SMS | Up-to-date OS, Passcode & Fingerprint enabled |
| Smart TV / Streaming Device | YouTube, Netflix | Media viewing history, linked Google account | Auto-updates enabled, protected by home Wi-Fi password |

---

### Online Accounts Inventory

| Account / Service | MFA Enabled? | Unique Password? | Potential Attacker Impact |
| --- | --- | --- | --- |
| Primary Email (Google) | Yes (App Authenticator) | Yes | Reset passwords for almost all linked services, access personal communications and cloud drives. |
| Primary Bank Account | Yes (Strong Mobile Auth) | Yes | Perform unauthorized transfers, access account balances and transaction histories. |
| GitHub Account | Yes (Security Key / App) | Yes | Overwrite source code repositories, delete personal portfolios, or push malicious commits. |
| Social Media (Discord/LinkedIn) | Yes | Yes | Impersonate identity, send phishing links to contacts, scam acquaintances. |
| School / M365 Account | Yes (SMS/Push) | Yes | Access course materials, internal communications, and cloud documents. |

---

### Top 5 Highest-Value Targets

1. **Primary Google Account:** This is the single point of failure because it serves as the recovery address for almost all other services. If compromised, an attacker could trigger password resets across my entire digital footprint.
2. **Online Banking Access:** While financial transactions require mobile authentication, unauthorized access could expose financial history or lead to fraudulent activity attempt.
3. **Primary Smartphone:** My phone holds active sessions for critical apps and hosts 2FA authenticators. Physical or remote compromise could bypass two-factor security mechanisms.
4. **GitHub Account:** My GitHub hosts my academic coursework, portfolios, and code repositories. Compromise could result in lost work or reputation damage if malicious code is pushed under my name.
5. **School / M365 Account:** Contains access to internal educational portals, assignments, and group communications. Unauthorized access could disrupt my studies or compromise personal academic data.

---

### Personal Reflection

My biggest exposure lies in how heavily my personal security relies on my primary email account and smartphone. Even though I have Multi-Factor Authentication enabled on major accounts, my phone acts as a hub for authenticator apps, SMS verification codes, and active logins. If my phone were lost or compromised while unlocked, an attacker could potentially gain access to several connected services before I could revoke permissions remotely. Additionally, having multiple active browser sessions saved on my laptop increases session-hijacking risks if malware ever executes locally.

One concrete change I will make this week is to audit my active browser sessions and log out of sensitive accounts on devices where stay-logged-in features aren't strictly necessary. I will also back up my authenticator app recovery keys to an encrypted offline location so that I can quickly regain control of my accounts if my mobile device is ever lost or damaged.
