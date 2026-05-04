# Course 3 — IBM Cybersecurity Tools and Cyberattacks

**Certificate:** [Verify here](https://coursera.org/verify/YBNM3CSMSXPS)
**Completed:** April 5, 2026

---

## My 5-Line Summary

1. This course taught how attacks happen step by step and what tools defenders use to stop them
2. Attacks follow 7 predictable stages called the Cyber Kill Chain — if you know the stage you can stop the attacker
3. Windows Group Policy Editor (gpedit) lets you enforce password rules for all users on a Windows computer
4. SOC analysts map suspicious activity to Kill Chain stages to understand how far an attack has gone
5. Interview question: Walk me through the Cyber Kill Chain. What password policies prevent brute force attacks?

---

## Cyber Kill Chain — All 7 Stages

| Stage | What Attacker Does | How to Stop It |
|-------|--------------------|----------------|
| 1. Reconnaissance | Researches the target — LinkedIn, website, DNS | Limit public information |
| 2. Weaponisation | Creates the malware or attack tool | Nothing to detect here |
| 3. Delivery | Sends phishing email or malicious link | Email filtering, user training |
| 4. Exploitation | Uses vulnerability to get inside the system | Patching, IDS/IPS |
| 5. Installation | Installs malware, creates backdoor | Antivirus, endpoint detection |
| 6. Command and Control | Malware calls home, attacker takes control | Firewall, DNS monitoring |
| 7. Actions on Objectives | Steals data, encrypts files, causes damage | DLP, network segmentation |

---

## IBM Lab 1 — Password Strength Testing

**Tool used:** password.kaspersky.com

| Password | How Long to Crack | Why |
|----------|------------------|-----|
| fido1973 | Seconds | Pet name plus birth year — very predictable |
| Fido1973! | Hours to days | Better but still a real word |
| Mh1llifwwas! | Many years | Acronym of a phrase — completely unpredictable |

**Key lesson:** Length matters more than complexity. A 12-character passphrase acronym is much stronger than a short 8-character password with symbols.

---

## IBM Lab 2 — Windows Password Policy Using gpedit

**Path I followed:**
Computer Configuration > Windows Settings > Security Settings > Account Policies > Password Policy

**Settings I configured:**

| Setting | Value | Why |
|---------|-------|-----|
| Enforce password history | 24 | Stops reusing old passwords |
| Maximum password age | 60 days | Forces regular password changes |
| Minimum password age | 1 day | Stops changing back immediately |
| Minimum password length | 12 characters | Short passwords are easily brute forced |

---

## Interview Answers I Prepared

**Q: Walk me through the Cyber Kill Chain.**
Stage 1 Reconnaissance — attacker gathers information. Stage 2 Weaponisation — creates the attack. Stage 3 Delivery — sends it to the victim. Stage 4 Exploitation — runs the attack. Stage 5 Installation — makes it permanent. Stage 6 Command and Control — attacker controls it remotely. Stage 7 Actions on Objectives — steals data or encrypts files.

**Q: What password policies prevent brute force attacks?**
Minimum password length of 12 characters, complexity requirements, and most importantly an account lockout policy — lock the account after 5 failed attempts. This completely stops brute force. Also set password history to 24 so users cannot reuse compromised passwords.
