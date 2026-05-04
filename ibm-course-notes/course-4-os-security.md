# Course 4 — IBM OS Overview, Administration and Security

**Certificate:** [Verify here](https://coursera.org/verify/81RQLE9EBSB0)
**Digital Badge:** [Verify on Credly](https://www.credly.com/badges/9e6bc8cb-cbce-41b8-95e5-8c3d30a238d4)
**Completed:** April 22, 2026

---

## My 5-Line Summary

1. This course taught how operating systems work, how to administer them, and how to secure both Windows and Linux
2. The principle of least privilege — every user gets ONLY the permissions they need, nothing extra — limits damage if an account is hacked
3. Windows Event Logs record every action on a computer with an Event ID number — SOC analysts read these to detect attacks
4. When a SIEM alert fires a SOC analyst reads Event Logs to see exactly what happened — which user, which process, what time
5. Interview question: Which Event ID detects failed login? (Answer: 4625). What is least privilege?

---

## Windows Event IDs — Must Memorise for SOC Job

| Event ID | What It Means | Why SOC Cares |
|----------|--------------|---------------|
| 4624 | Successful login | Suspicious if at 3am or strange location |
| 4625 | FAILED login | Many in a row = brute force attack happening NOW |
| 4688 | New process created | Malware often appears here when it runs |
| 4698 | Scheduled task created | Hackers use this to make malware run after reboot |
| 4720 | New user account created | Hacker might be creating a backdoor account |
| 7045 | New service installed | Common malware installation method |
| 1102 | Audit log was cleared | VERY suspicious — attacker covering their tracks |

---

## OS Security Concepts

### Principle of Least Privilege
Give people only the access they need for their job — nothing more.
Example: A marketing employee should NOT have admin access to the server.
If their account is hacked, the attacker also only gets marketing-level access — limiting damage.

### Windows User Account Types
- Standard User: normal person — cannot install software
- Administrator: full control — high risk if hacked
- Guest: very limited — for temporary visitors
- Service Account: used by programs to run — often targeted by hackers

### OS Hardening Rules
1. Remove software you do not need
2. Update and patch everything regularly
3. Turn off services and ports you do not use
4. Give everyone minimum permissions only
5. Turn on logging so you can see everything that happens
6. Use strong passwords and MFA everywhere

---

## Interview Answers I Prepared

**Q: What is the principle of least privilege?**
Everyone gets only the minimum access they need for their job. If a marketing employee does not need server admin access, they should not have it. If their account is compromised, least privilege means the attacker also has limited access — reducing the damage they can cause.

**Q: Which Event ID tells you a brute force attack is happening?**
Event ID 4625 shows failed login attempts. If I see many 4625 events from the same IP address in a short time, that is a brute force attack. I would also check if any 4624 successful login followed those failures — that would mean the brute force succeeded and the account is compromised.
