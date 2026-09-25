# Social Engineering Tabletop Exercise: Pohjola Logistics Oy

## Goal
Build practical recognition of social engineering tactics by analyzing attack vectors, designing defensive playbooks, and evaluating security controls for Pohjola Logistics Oy as part of Cisco Module 2.

## Steps
1. Analyzed the organizational facts and attack surfaces of Pohjola Logistics Oy (SME with 80 employees, M365 usage, outsourced MSP, active CEO on LinkedIn).
2. Selected an attack vector to design a realistic scenario (IT MSP Pretexting / Phishing).
3. Developed comprehensive defense playbooks covering Recognition, Immediate Action, Verification, Escalation, Recovery, and Prevention across all key vectors.
4. Performed a cross-group critique comparing defensive controls against potential evasion tactics.

---

## Findings

### Phase 2: Attacker Scenario (Vector: Pretexting IT MSP)

* **Target selection:** Junior Finance Administrator at Pohjola Logistics Oy. Targeted because they have M365 access, authorization to handle routine internal processes, and may be quick to comply with urgent technical requests from an "IT administrator."
* **Reconnaissance (OSINT):** Checked the CEO’s public LinkedIn profile to identify key vendors, extracted email formatting patterns (`firstname.lastname@pohjolalogistics.fi`), and identified the regional IT Managed Service Provider (MSP) usually tagged in local Finnish tech posts.
* **Pretext:** Impersonating an IT support technician from the outsourced local MSP who is handling an urgent critical security patch for Microsoft 365 accounts across Pohjola Logistics.
* **Hook:** Creating urgency by stating that the target's M365 account has flagged suspicious sign-ins, and failure to complete a immediate password validation will lead to account lock-out during business hours.
* **Execution (Scenario Script Overview):** 
  * *Email/Phone message:* "Hei, this is Mikko from IT Service Desk. We are applying a mandatory M365 security patch for Pohjola Logistics staff today. Please confirm your current login details on the updated verification portal [fake-link] within 15 minutes to avoid account suspension."
* **Indicators (Red Flags):** 
  * The request bypasses the standard internal ticketing system process.
  * The link URL does not match the official MSP domain or standard Microsoft M365 login endpoints.
  * High sense of artificial urgency threatening account suspension.

---

## Phase 2: Defender Playbooks

### 1. Phishing Email Targeting Finance
* **Recognition:** External email tag, mismatched domain in sender address, urgent demands regarding invoice/payment changes, or suspicious links/attachments.
* **Immediate action:** Do not click links, open attachments, or reply. Leave the email untouched in the inbox.
* **Verification:** Call the internal requester or supplier directly using a pre-verified phone number from official records (never use contact details inside the suspicious email).
* **Escalation:** Report via M365 "Report Phishing" button and notify the internal IT/MSP contact via ticket.
* **Recovery:** If clicked, immediately disconnect the machine from Wi-Fi/Ethernet and notify IT to reset credentials and terminate active sessions.
* **Prevention:** Enforce strict Multi-Factor Authentication (MFA) and implement strict SPF, DKIM, and DMARC policies.

### 2. Vishing Call to HR
* **Recognition:** Phone caller claiming to be an applicant or authority figure demanding urgent action, password resets, or personal employee data over the phone.
* **Immediate action:** Refuse to disclose sensitive personal data or system credentials over an incoming call.
* **Verification:** Request caller details, hang up, and call back using the official phone number listed in public applications or official documentation.
* **Escalation:** Log the caller ID, time, and requested details, then forward the log to HR Lead and IT Security.
* **Recovery:** If sensitive information was shared, immediately alert IT to restrict compromised accounts or notify impacted personnel.
* **Prevention:** Establish a strict policy that no credentials or sensitive employee data are ever verified or altered via incoming voice calls.

### 3. Pretexting (Impersonation of Outsourced IT MSP)
* **Recognition:** Unsolicited communication requesting credentials, MFA codes, or remote access outside standard ticket procedures.
* **Immediate action:** Pause the interaction and decline granting remote access or sharing account details.
* **Verification:** Check the official MSP ticketing portal or contact the designated internal Pohjola IT coordinator.
* **Escalation:** Submit an incident ticket through the official MSP portal reporting unauthorized impersonation.
* **Recovery:** Revoke any granted remote session tools immediately, reboot the host system, and trigger an forced password reset.
* **Prevention:** Implement a mandatory two-way verification protocol for all IT support requests (e.g., ticket number matching).

### 4. Physical Tailgating at Vantaa Office / Tampere Warehouse
* **Recognition:** Unidentified individuals following employees closely through access-controlled doors without badges.
* **Immediate action:** Polite confrontation ("May I help you find someone?") or holding the door shut until keycard authentication occurs.
* **Verification:** Ask for visitor badge, employee ID, or host name.
* **Escalation:** Notify facility management or security personnel immediately if the individual refuses to identify themselves.
* **Recovery:** Escort the unauthorized person to the reception area and audit recent access logs.
* **Prevention:** Install turnstiles/electronic keycard access and conduct regular physical security awareness training for all staff.

---

## Phase 3: Cross-Group Critique

### Defender Evaluation of Attacker Scenario
* **Would our playbook have caught this?** Yes, the pretexting playbook specifically instructs employees to verify any IT request against the official MSP ticketing system rather than following external links.
* **Where would it fail?** It could fail if the employee panics due to the 15-minute deadline threat and bypasses standard verification out of fear of work disruption.
* **What would we add?** Add automated technical controls like external email banner warnings and domain-level blocking of newly registered domains.

### Attacker Evaluation of Defender Controls
* **Could we have evaded these controls?** Evasion would be possible by using a phone call first to establish rapport (vishing) before sending the email, making the interaction feel more authentic.
* **What's the weakest link in this playbook?** The weakest link is human compliance under pressure; reliance on manual employee verification leaves room for human error when urgent operational tasks are involved.
