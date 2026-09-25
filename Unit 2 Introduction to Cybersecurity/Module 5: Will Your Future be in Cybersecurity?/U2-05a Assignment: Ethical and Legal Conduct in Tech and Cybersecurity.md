# Ethical and Legal Conduct in Tech and Cybersecurity

## Goal
Establish a clear understanding of legal and ethical boundaries in entry-level IT and cybersecurity roles by working through realistic workplace dilemmas and defining a personal code of conduct.

## Steps
1. Reviewed key legal frameworks including Chapter 38 of the Finnish Criminal Code (*Rikoslaki*) regarding unauthorized access, alongside GDPR and *Tietosuojalaki* principles.
2. Evaluated five realistic workplace ethical dilemmas, analyzing legal risks, ethical stakes, and concrete action steps for each.
3. Drafted and signed a personal Code of Conduct to serve as a binding reference point for professional tech work.

---

## Scenario Responses

### Scenario 1: The colleague's password

**What is happening (in my own words):**
A senior colleague and helpful mentor asks me to log into her locked computer using her plaintext password so I can check a support ticket for her while she is on a phone call. She is sharing her credentials directly with me out of operational frustration and urgency to avoid putting a customer on hold.

**What's legally at stake:**
Sharing and using another individual's credentials violates company Acceptable Use Policies (AUP) and compromises audit logs, making actions taken on that account non-repudiable under Finnish data protection frameworks. Logging into another person's account, even with their verbal permission, blurs the legal boundary of "authorization" under the Criminal Code (*Rikoslaki* Chapter 38) because system logs will falsely attribute my actions to her identity.

**What's ethically at stake:**
At stake is the principle of personal accountability and mutual professional trust. While helping a helpful mentor feels like the right social choice, using her credentials compromises system integrity and exposes both of us to severe liability if anything goes wrong during that active session.

**What I would do:**
I would decline to enter her credentials into her computer. Instead, I would offer to pull up ticket #4521 directly on my own workstation using my own authenticated account while she finishes her call. If I do not have direct permission to view that specific ticket queue, I would ask her to briefly put the customer on hold or wait 30 seconds so she can unlock her own screen.

**What I would NOT do, and why:**
I would not type her password into her computer or log into her account under any circumstances. Doing so sets a dangerous precedent of credential sharing and violates core identity management rules.

**Who I would consult:**
I would address this privately with my colleague after her call, explaining that I wanted to protect both her account and mine from policy violations. If password sharing is a widespread culture in the team, I would bring it up with the Service Desk Team Lead during our next 1-on-1.

---

### Scenario 2: The found credentials

**What is happening (in my own words):**
While replacing a keyboard at an unattended manager's desk, I discover an old sticky note hidden underneath containing what looks like a Domain Admin password. No one is around to witness the discovery, and the password appears to have been sitting there for a long time.

**What's legally at stake:**
The existence of an exposed Domain Admin password violates basic organizational security policies and access control requirements under GDPR safeguards. Utilizing or storing those credentials without authorization would constitute an offence under the Finnish Criminal Code (*Rikoslaki*) regarding unauthorized access to administrative systems.

**What's ethically at stake:**
The dilemma centers on honesty versus the temptation of unauthorized curiosity. Holding administrative power without explicit responsibility creates an immense ethical conflict between upholding professional integrity and misusing system access.

**What I would do:**
I would leave the sticky note in place temporarily without copying, photographing, or testing the password. I would finish the keyboard replacement, ensure the workstation remains locked, and immediately report the physical credential exposure directly to my supervisor or the IT Security Officer so the account password can be forcibly rotated.

**What I would NOT do, and why:**
I would not test the password on any system, save it to my phone, or attempt to log into administrative interfaces to see if it still works. Testing it constitutes unauthorized access regardless of my intentions.

**Who I would consult:**
I would consult my immediate Support Supervisor or the internal IT Security / CISO team immediately after completing the physical task.

---

### Scenario 3: The personal data peek

**What is happening (in my own words):**
A friend in another department asks me to use my technical read access on the helpdesk to look into the HR mailbox and retrieve her recent performance review email because she is worried about her job standing. She wants me to bypass official HR channels to give her early access to her own review files.

**What's legally at stake:**
This directly violates the GDPR principle of "Purpose Limitation" and "Need-to-Know Access" enforced under Finnish data protection law (*Tietosuojalaki*). Technical access privileges do not equal legal authorization; accessing HR mailboxes without an explicit support ticket for that specific mailbox constitutes a breach of confidentiality and a punishable offense.

**What's ethically at stake:**
The conflict pits personal loyalty to a friend against professional ethics, employer trust, and data privacy principles. Misusing administrative privileges to spy on HR records undermines organizational fairness and betrays the trust placed in support staff.

**What I would do:**
I would firmly refuse my friend's request and explain that using my technical access to view HR mailboxes without a formal ticket is illegal and would cost me my job. I would empathetically advise her to contact her HR representative or line manager directly to request a copy of her review through official channels.

**What I would NOT do, and why:**
I would not open, search, or forward any HR emails or employee files for my friend. Tempting as it is to reassure a worried colleague, abusing helpdesk privileges is a direct breach of employment ethics.

**Who I would consult:**
If my friend continues to press me or attempts to pressure me into misusing my access, I would inform my Service Desk Manager about the request to protect myself from potential false accusations later.

---

### Scenario 4: The vulnerability you accidentally noticed

**What is happening (in my own words):**
While using my employer’s customer portal for personal use, I notice that changing the `userId` parameter in the browser URL loads another customer's private order history. I accidentally stumbled upon an Insecure Direct Object Reference (IDOR) vulnerability exposing customer data without needing complex tools.

**What's legally at stake:**
Manipulating URL parameters to access data belonging to other accounts falls under unauthorized data access under Chapter 38 of the Finnish Criminal Code. Under GDPR, the exposure of customer order histories via an IDOR flaw constitutes a reportable personal data breach that the company must report to the Data Protection Ombudsman (*Tietosuojavaltuutettu*) within 72 hours.

**What's ethically at stake:**
The ethical choice involves responsible disclosure versus ignoring a security flaw or actively exploiting it. As an employee and customer, I have an ethical obligation to protect customer privacy by reporting the vulnerability responsibly without conducting further unauthorized testing.

**What I would do:**
I would immediately stop altering parameters and close the browser session without accessing any further customer records. I would write down the exact URL structure I observed on my own account and submit a confidential, professional vulnerability report to the internal IT Security team or CISO, detailing how the flaw was accidentally discovered.

**What I would NOT do, and why:**
I would not alter additional `userId` numbers to test the scale of the bug, scrape data, or share the URL flaw with colleagues or external parties. Further probing crosses the line into unauthorized penetration testing.

**Who I would consult:**
I would consult the internal IT Security / Security Operations Center (SOC) team or the Lead Systems Administrator immediately via official internal reporting channels.

---

### Scenario 5: The off-hours request

**What is happening (in my own words):**
A friend working at another company asks me to perform off-hours security testing on his company's website because it has been acting strangely. He claims that because he works in IT, his verbal request gives me permission to scan or inspect their web infrastructure over the weekend.

**What's legally at stake:**
Conducting security testing or vulnerability scanning without explicit, written authorization from the system owner is a crime under Chapter 38 of the Finnish Criminal Code. An IT employee's verbal request does not constitute legal authorization on behalf of an entire corporation; performing scans without a signed contract or formal scope exposes me to severe criminal liability.

**What's ethically at stake:**
At stake is recognizing the boundaries of my skills and authority. Accepting an informal request to test a live commercial system undermines professional cybersecurity standards and endangers a third-party organization's operational stability.

**What I would do:**
I would politely decline to perform any scans or vulnerability assessments on his company's website. I would explain that legal security assessments require formal written contracts signed by authorized executive management, and advise him to report the website anomalies through his company's official IT incident management process or engage a certified third-party security firm.

**What I would NOT do, and why:**
I would not run automated tools, vulnerability scanners, or manual injection tests against his company's servers. "Verbal permission" from a friend in IT provides zero legal defense against unauthorized testing charges.

**Who I would consult:**
I would not need to consult internal management as this is an external request, but I would advise my friend to consult his company's CISO or IT Director.

---

## Personal Code of Conduct

1. **Explicit Authorization First:** I will not log into, scan, or interact with any account, system, or network that I have not been explicitly authorized in writing to access, regardless of convenience or verbal requests from colleagues.
2. **Access Privilege Separation:** I will treat my technical administrative access to systems and personal data as a strict responsibility, accessing user files and mailboxes exclusively when required by a documented, official support ticket.
3. **Strict Credential Integrity:** I will never share my personal or professional login credentials with anyone, nor will I use another individual's credentials, ensuring that all system actions remain accurately auditable.
4. **Immediate Responsible Disclosure:** When I accidentally discover a security vulnerability in any system, I will cease all testing immediately and report the flaw privately to the responsible security authority without further probing or public disclosure.
5. **Data Minimization and Privacy:** I will handle all personal data in strict compliance with GDPR principles, collecting and viewing only the absolute minimum information required to complete my assigned tasks.
6. **No Informal Security Audits:** I will not perform external security testing, vulnerability scanning, or penetration testing without a legally binding, written contract signed by authorized corporate representatives.

---
Signed: Christo Topali  
Date: 2026-09-25  
First commit (initial version): 2026-09-25
