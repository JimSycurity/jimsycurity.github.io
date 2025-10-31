---
title: AdminSDHolder Blog and E-Book
creation_date: October 31, 2025
modification_date: October 31, 2025
tag: activedirectory
---

As you may be able to tell by my domain name, I'm partial to AdminSDHolder. It's one of my favorite Active Directory nich topics. It's part of my personal brand. And now, I literally wrote the e-book on AdminSDHolder.

Head to https://specterops.io/resources/adminsdholder/ to download the 159 page E-Book in PDF format.

I also wrote a [little bit shorter blog](https://specterops.io/blog/2025/10/31/adminsdholder-misconceptions-misconfigurations-and-myths/) to sumarize the topic in at least a hundred less pages.

Why am I so interested in AdminSDHolder? Well, it's one of the cornerstone security mechanisms in Active Directory. It's been around since Windows Server 2000 brought Active Directory to us 25+ years ago. And it's something that much of the Internet is confidently wrong about.  Even Microsoft's primary documentation on AdminSDHolder gets several important details incorrect.

<!-- excerpt-end -->

You can also check out the related [GitHub repo](https://github.com/JimSycurity/AdminSDHolder) which contains data points, scriptlets, lab results, and a [little side story](https://github.com/JimSycurity/AdminSDHolder/blob/main/Misc/DefaultAdminSDHolderMalformedACEs.md) about how Microsoft has included malformed Access Control Entries in the default AdminSDHolder security descriptor since the first release of Windows Server 2000.

If for some reason the links on the SpecterOps website aren't working, the [full PDF is available here](https://adminsdholder.com/files/AdminSDHolder_Misconceptions-Misconfigurations-v1.pdf) as well.