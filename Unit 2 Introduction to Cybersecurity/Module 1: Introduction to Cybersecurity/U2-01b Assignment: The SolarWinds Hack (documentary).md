# SolarWinds Incident Reflection

## Goal
Reflect on the SolarWinds incident and connect it to Cisco Module 1 concepts.

## Steps
1. Watched the documentary about the SolarWinds supply chain attack: [The SolarWinds Hack](https://www.youtube.com/watch?v=...)
2. Took notes on the timeline, attack vectors, and discovery of the breach.
3. Prepared this reflection connecting the real-world events to core cybersecurity principles.

---

## Findings

### 1. The incident in your own words
The SolarWinds incident was a major cyber espionage operation where attackers managed to hide malicious code inside a legitimate software update for SolarWinds Orion. When customers downloaded the normal routine update, they unknowingly gave the hackers a backdoor into their networks. It allowed foreign intelligence actors to spy on government agencies and huge corporations without raising immediate alarms.

### 2. Who was affected, and how?
The main victims included US government departments like Homeland Security and the Treasury, along with thousands of private companies like Microsoft and FireEye. The broader impact was huge because it wasn't just about stolen data; it was a major geopolitical threat that exposed critical infrastructure and compromised international security trust for months.

### 3. The CIA principle
Integrity was the primary CIA principle attacked because the hackers compromised the trust of the software build process by inserting malicious code into official updates. Confidentiality was heavily damaged right after, as the backdoor gave attackers unauthorized access to sensitive files and internal communications. Availability wasn't really the focus, since the attackers wanted to stay hidden rather than shut systems down.

### 4. The attack technique - what made this one different?
A supply chain attack targets a trusted third-party vendor instead of going directly after the final victim. This makes it far more dangerous than a standard direct attack because organizations naturally trust updates coming from vendors they pay for. By breaching one central software provider, the attackers instantly gained access to thousands of high-value targets all at once.

### 5. How was it discovered?
Surprisingly, the breach wasn't caught by SolarWinds or government monitoring systems, but by FireEye, a private security firm that noticed suspicious activity on their own network. This shows that cyberattacks often go undetected for a long time until an anomaly triggers a manual investigation by chance or thorough internal auditing.

### 6. What could have helped
Implementing stricter code signing security and multi-factor authentication across the entire software development pipeline could have limited the damage. If SolarWinds had better internal monitoring on build servers, they might have caught unauthorized changes before the malicious update was digitally signed and sent out to clients.

### 7. The broader lesson
The biggest lesson was that trusting reputable software blindly is a major security risk. It proved to the cybersecurity industry that modern supply chains are extremely fragile, and even established enterprise security vendors can become entry points for sophisticated nation-state hackers.

### 8. Your personal takeaway
This documentary made me think twice about software updates and default trust. I used to assume that official updates were always safe, but now I realize that zero-trust principles need to apply to third-party software as well, not just untrusted networks or users.
