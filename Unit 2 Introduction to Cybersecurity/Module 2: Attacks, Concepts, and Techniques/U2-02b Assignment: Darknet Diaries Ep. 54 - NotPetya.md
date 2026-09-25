# Darknet Diaries Ep. 54: NotPetya Reflection

## Goal
Reflect on the NotPetya cyberattack from Darknet Diaries Ep. 54 and connect it to Cisco Module 2 concepts regarding attack techniques, supply chain infiltration, and data destruction.

## Steps
1. Listened to Darknet Diaries Episode 54 covering the history, mechanics, and impact of NotPetya.
2. Took notes on the supply chain vector (M.E.Doc), internal network propagation methods, and total organizational impact.
3. Prepared this structured reflection connecting the real-world event to Module 2 cybersecurity principles.

---

## Findings

### 1. The incident in your own words
NotPetya was a destructive cyberattack launched in June 2017 that initially targeted Ukraine before spreading rapidly across global corporate networks. Unlike WannaCry's random internet-wide scanning, NotPetya originated from a compromised Ukrainian accounting software update and automatically jumped across interconnected business networks. Within hours, it encrypted master boot records and hard drives worldwide, completely paralyzing systems regardless of geographic borders.

### 2. Who was affected, and how
The attack hit multinational corporations operating in Ukraine, including shipping giant Maersk, pharmaceutical company Merck, and FedEx subsidiary TNT Express. For Maersk, NotPetya wiped tens of thousands of servers and user PCs in minutes, halting global shipping logistics and forcing port terminals to stall completely. Overall, the global financial impact was estimated at over $10 billion, making it one of the costliest cyberattacks in history.

### 3. The CIA principle - and the trick
Availability and Integrity were the real targets of this attack, as NotPetya irreversibly destroyed file systems and prevented organizations from accessing critical operational data. The "fake ransomware" framing was a deliberate deception trick used by the attackers to disguise a state-sponsored wiper as a petty cybercrime scheme. By demanding ransom for decryption keys that were mathematically impossible to generate, the attackers hid their true goal of causing pure destruction.

### 4. The attack technique - initial access through a supply chain
The attackers gained initial access by breaching M.E.Doc, a small Ukrainian tax software company that almost every business operating in Ukraine was required to use. They compromised M.E.Doc's software update server to push malicious code directly to users disguised as a legitimate software update. Targeting an update mechanism is extremely powerful because trusted, signed software updates bypass standard security firewalls and antivirus protections automatically.

### 5. How it spread inside networks
Once inside a single machine, NotPetya combined the EternalBlue exploit with credential-harvesting tools like Mimikatz to steal administrative credentials from memory. This allowed the malware to move laterally through internal networks using legitimate administrative tools like PsExec and WMI. Because it used stolen credentials, it could log into and infect fully-patched Windows machines that were otherwise immune to EternalBlue alone.

### 6. What could have helped
Strict network segmentation and restricting domain administrator privileges would have significantly limited NotPetya's lateral movement. If the networks connecting foreign branch offices to Ukrainian operations had been properly isolated, the malware would not have been able to leverage administrative credentials to spread across an entire enterprise network so rapidly.

### 7. The broader lesson - attribution and consequences
NotPetya demonstrated that cyber weapons are almost impossible to contain once released into the wild, especially when targets are connected to global supply chains. The attack was attributed to Russian military intelligence aiming to disrupt Ukraine's economy, but the unintended collateral damage crippled international commerce. It highlighted how modern geopolitics and state cyber operations can instantly impact innocent private businesses worldwide.

### 8. Your personal takeaway
The biggest takeaway for me was realizing how fragile global corporate IT infrastructure actually is when trusted software is weaponized. I realized that keeping a system patched isn't a silver bullet on its own if an attacker already holds legitimate administrative privileges inside the network.
