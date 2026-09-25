# CIA Triad Case Studies

Analysis of four incident scenarios applying the CIA Triad principles (Confidentiality, Integrity, Availability) to evaluate primary violations, secondary impacts, attack techniques, and controls.

---

## Scenario A: The Hospital

### Primary CIA Violation
**Availability**

### Secondary Impacts
* **Confidentiality:** The attackers exfiltrated a sample of patient files and threatened to publish them, compromising private medical data.
* **Integrity:** The encryption of patient records on file servers corrupted the state and usability of live operational records, making them temporarily unusable for staff.

### Attack Technique
* Ransomware
* Data Exfiltration (Double Extortion)

### Preventive Controls
1. **Network Segmentation:** Isolate critical medical systems, patient file servers, and administrative networks to prevent lateral movement.
2. **Email & Endpoint Security:** Implement advanced email filtering to block phishing payloads alongside Endpoint Detection and Response (EDR) solutions.
3. **Patch Management:** Regularly apply security updates to operating systems and applications to eliminate known vulnerabilities.

### Damage-Limitation Controls
1. **Offline and Immutable Backups:** Maintain isolated, regular backups to allow fast system restoration without paying the ransom.
2. **Incident Response Plan & Data Loss Prevention (DLP):** Execute a predefined incident response plan to isolate infected segments quickly and deploy DLP tools to detect large unauthorized data transfers.
3. **Business Continuity Planning (BCP):** Establish manual operational procedures (e.g., paper-based patient tracking) to maintain emergency services during downtime.

---

## Scenario B: The Leaked Database

### Primary CIA Violation
**Confidentiality**

### Secondary Impacts
* **Integrity:** The use of weak MD5 password hashes leaves user credentials vulnerable to cracking and potential unauthorized modifications via account takeover.
* **Availability:** Potential need to temporarily take down public portal login services to force global password resets and audit compromised accounts.

### Attack Technique
* Data Exfiltration / Database Exfiltration (e.g., via SQL Injection or credential theft)

### Preventive Controls
1. **Input Validation & Parameterized Queries:** Prevent common web application flaws like SQL Injection that allow unauthorized access to underlying databases.
2. **Strong Password Hashing:** Use modern, salted hashing algorithms (such as bcrypt, Argon2, or PBKDF2) instead of outdated MD5.
3. **Least Privilege & Access Control:** Restrict database user permissions so web applications only access necessary data tables.

### Damage-Limitation Controls
1. **Forced Password Resets & Session Revocation:** Immediately invalidate existing user sessions and mandate password updates for all customers.
2. **Database Auditing & Alerting:** Monitor for abnormal query volumes or massive database exports to detect and break off data exfiltration in real time.
3. **Incident Communication & Customer Support:** Promptly notify affected customers and financial partners (for partial card data) to minimize fraudulent use.

---

## Scenario C: The Defaced Municipal Site

### Primary CIA Violation
**Integrity**

### Secondary Impacts
* **Availability:** The public website was intentionally taken offline for 4 hours while technical staff restored clean files from backups.
* **Confidentiality:** If the defacement resulted from stolen administrative credentials, unauthorized parties may have accessed internal site structures or management panels.

### Attack Technique
* Web Site Defacement (via Content Management System vulnerability, file upload flaw, or compromised admin credentials)

### Preventive Controls
1. **Web Application Firewall (WAF):** Deploy a WAF to filter out malicious web requests and block common exploitation payloads targeting web software.
2. **Multi-Factor Authentication (MFA) & Strong Access Controls:** Require MFA for all CMS admin panels and SSH/FTP access to prevent account hijacking.
3. **Software & Plugin Updates:** Keep the web server, CMS core, and third-party plugins regularly updated to patch security bugs.

### Damage-Limitation Controls
1. **File Integrity Monitoring (FIM):** Implement FIM tools to detect unauthorized file changes on the web server instantly and automatically alert admins.
2. **Automated Clean Backups:** Use frequent, automated off-site backups to allow quick rollback to a known good state.
3. **Static Page Fallback:** Configure a temporary maintenance or static landing page to keep basic public notifications available during remediation.

---

## Scenario D: The Manipulated Invoice

### Primary CIA Violation
**Integrity**

### Secondary Impacts
* **Confidentiality:** The attacker compromised the supplier’s email account, allowing them to read private business correspondence and billing details.
* **Availability:** Financial operations were disrupted, delaying actual payment processing to the legitimate supplier and impacting business workflow.

### Attack Technique
* Business Email Compromise (BEC)
* Email Account Compromise (EAC) / Man-in-the-Middle (MitM) invoice tampering

### Preventive Controls
1. **Dual-Control Payment Verification:** Implement an out-of-band verification policy (e.g., confirming any bank detail changes via a known phone number) before processing transactions.
2. **Email Authentication Protocols:** Enforce SPF, DKIM, and DMARC policies on email domains to reduce email spoofing and suspicious incoming mail.
3. **Multi-Factor Authentication (MFA) on Email:** Enforce MFA across all employee email accounts to prevent initial account compromise.

### Damage-Limitation Controls
1. **Financial Revocation Protocols:** Immediately contact the sending and receiving banks to flag the fraudulent transfer and request a recall of funds.
2. **Compromised Account Remediation:** Force password resets, revoke active sessions, and audit email routing/forwarding rules on compromised accounts.
3. **Incident Reporting:** Notify local law enforcement and cybersecurity authorities to trace financial transfers and attempt asset recovery.
