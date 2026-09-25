# WannaCry Ransomware Attack Reflection

## Goal
Reflect on the WannaCry ransomware incident and connect it to Cisco Module 1 concepts.

## Steps
1. Watched the documentary about the 2017 WannaCry global ransomware attack.
2. Took notes on the EternalBlue exploit, network propagation, affected systems, and the kill switch discovery.
3. Prepared this structured reflection connecting real-world impact to foundational cybersecurity concepts.

---

## Findings

### 1. The incident in your own words
In May 2017, the WannaCry ransomware outbreak spread across the globe at an unprecedented speed, infecting over 200,000 computers in more than 150 countries within hours. It targetted computers running older or unpatched Windows operating systems, encrypting user files and demanding a Bitcoin ransom to restore access. Because it propagated automatically over local networks and the internet without needing users to click anything, it caused massive chaos almost instantly.

### 2. Who was affected, and how
The attack hit a massive range of organizations, including logistics companies like FedEx, telecom providers, and government agencies. The most severe human impact was felt in the UK, where the National Health Service (NHS) was heavily paralyzed, forcing hospitals to cancel non-urgent surgeries, divert ambulances, and revert to pen and paper. The timing was particularly disastrous because critical public services relied on outdated infrastructure that couldn't handle a sudden, widespread digital lockout.

### 3. The CIA principle
Availability was the primary CIA principle attacked, as the ransomware locked systems and encrypted critical files, completely preventing authorized users from accessing essential services and medical systems. Confidentiality was less affected because the attackers focused on locking data rather than exfiltrating it, while Integrity was compromised in the sense that the system files and data structures were altered into encrypted formats without user authorization.

### 4. The attack technique - ransomware and "wormable" exploits
Ransomware is malicious software designed to block access to a computer system or files until a sum of money is paid. What made WannaCry exceptionally dangerous compared to standard ransomware was its worm capability using the EternalBlue exploit, which allowed it to scan networks and infect vulnerable devices automatically. Typical ransomware relies on phishing links or manual execution by a user, but WannaCry needed no human interaction once it entered a network.

### 5. How was it discovered and how was it stopped
The attack was quickly noticed as emergency rooms and business systems simultaneously began displaying red ransom screens demanding Bitcoin payments. It was unexpectedly halted when security researcher Marcus Hutchins discovered an unregistered domain name hardcoded into the malware's source code and registered it, which accidentally triggered a built-in "kill switch." This shows that complex cyberattacks can sometimes be neutralized by chance or through quick, creative analysis of malware behavior under pressure.

### 6. What could have helped - the patch question
Many organizations had not applied Microsoft's patch prior to the attack because updating legacy systems often requires downtime, complex testing, or compatibility checks with older operational software. Aside from applying patches, having isolated, offline backups would have limited the damage, as organizations could have restored their systems without paying a ransom or relying on the kill switch. Network segmentation could have also stopped the ransomware from spreading laterally into critical subnets.

### 7. The broader lesson
WannaCry taught the world that delaying critical patches on public-facing networks creates massive operational vulnerability, especially in healthcare and utility sectors. It also highlighted the severe risks of intelligence agencies stockpiling zero-day vulnerabilities, as leaked government cyber-weapons can easily fall into malicious hands and cause collateral damage on a global scale.

### 8. Your personal takeaway
Watching this made me realize how dangerous it is to hit "remind me later" on system update notifications. I used to think of security updates as minor feature tweaks or slight annoyances, but now I see them as critical defensive measures that keep entire networks from falling apart.
