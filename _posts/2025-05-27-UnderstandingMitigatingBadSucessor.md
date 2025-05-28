---
title: Understanding & Mitigating BadSuccessor
creation_date: May 27, 2025
modification_date: May 27, 2025
tag: activedirectory
---
On May 21, 2025 Yuval Gorden of Akamai released his blog [BadSuccessor: Abusing dMSA to Escalate Privileges in Active Directory](https://www.akamai.com/blog/security-research/abusing-dmsa-for-privilege-escalation-in-active-directory), which details how the new [Delegated Managed Service Account](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/manage/delegated-managed-service-accounts/delegated-managed-service-accounts-overview) (dMSA) feature introduced to Active Directory by Windows Server 2025 can be abused to impersonate any security principal or potentially recover credentials from any security principal.

Only Microsoft can remediate the underlying issues around BadSuccessor, but in the meantime we can mitigate the issue by focusing on the DACL abuses required for the attacker to gain control of a dMSA.  I wrote up [Understanding & Mitigating BadSuccessor](https://specterops.io/blog/2025/05/27/understanding-mitigating-badsuccessor/) to explore the DACL abuse primitives and ways to mitigate them.  The blog also includes a reference to my [GitHub](https://github.com/JimSycurity/dMSAs) where I've included PowerShell scripts which automate the hard work of creating ACEs on OUs and containers where dMSA accounts could reside.

<!-- excerpt-end -->

# Understanding & Mitigating BadSuccessor
TL;DR: BadSuccessor is a new AD attack primitive that abuses dMSAs, allowing an attacker who can modify or create a dMSA to escalate privileges and take over the forest. The DACL-based parts of the attack have relatively straightforward mitigations.

Recently [Yuval Gordon](https://x.com/YuG0rd) at Akamai released the blog post [BadSuccessor: Abusing dMSA to Escalate Privileges in Active Directory](https://www.akamai.com/blog/security-research/abusing-dmsa-for-privilege-escalation-in-active-directory) with some great research on abusing a new managed service account type for Active Directory which was released in Windows Server 2025\. If you haven’t read that post in full yet, please do so before continuing on with this one.

In a nutshell, BadSuccessor allows anyone who can create or compromise a Delegated Managed Service Account (dMSA) in any AD Forest where at least 1 Windows Server 2025 Domain Controller (DC) is in place and a KDS Root Key has been generated to abuse the created or compromised dMSA to perform an Escalation of Privilege (EoP) to any security principal, including a member of Domain Admins. BadSuccessor can also be abused to recover the keys of a superseded account, which is a form of credential theft that can also result in full AD Forest compromise. 

...read the rest of the blog here: [Understanding & Mitigating BadSuccessor](https://specterops.io/blog/2025/05/27/understanding-mitigating-badsuccessor/)

### Companion Script Repo
https://github.com/JimSycurity/dMSAs