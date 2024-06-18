---
sidebar_label: "Is OpenSource Secure?"
sidebar_position: 67
---

# Is Open Source Secure?

PassHub.net is an open-source project. This means the PassHub source code is publicly available and can be viewed on GitHub: https://github.com/wwpass/passhub. Sometimes, this feature raises concerns and questions: is it safe enough? Or could it help malicious actors discover vulnerabilities on PassHub and steal users’ secrets?

## Transparency as a Security Feature 

PassHub.net, a password manager, stores and secures users’ login credentials, Google Authenticator codes, bank cards, document scans, and other extremely sensitive information. The first and most important question is: Why should someone trust PassHub.net?

Computer security practice provides a surprising answer: “Be open; show your code internals.” By making our code visible to the world, we invite peer review and collaboration, turning potential vulnerabilities into opportunities for strengthening our defenses. That is the ultimate response to “How can we trust you?”

## The Paradox of Closed-Source Security

Consider the opposite example: One of the top-10 password managers with closed code allows users to share password records with others before these peers have created an account. This looks suspicious and hardly aligns with the declared feature of “client-side encryption.” Such claims raise questions about how the encryption keys are managed and shared securely and if we can’t trust them to show us how they are doing this, how can we trust anything else they claim to do? 

In a world where threats are omnipresent, trust must be earned. Hiding the ball is a bad place to start. 

## Strength in Numbers

Due to the openness of the PassHub code, other developers can view our code and send us their findings and recommendations.

All cipher algorithms (RSA, AES, etc.) are published and thoroughly documented. Modern computer security is a matter of math. The idea behind it is that algorithms are open, and only the cipher keys are the real secrets that should be kept hidden. Instead of trying to keep megabytes of source code secret, we just secure a dozen or two bytes. This approach sounds fantastic and has been learned through practice: every time a closed algorithm was declared the “strongest one,” it was cracked within weeks. The story of the NSA’s “digital fortress” is a good example.

Another question regarding open source: PassHub uses third-party open-source libraries and modules. How can one be sure there are no hidden backdoors?

The main building blocks of the modern IT software stack are also open: Linux OS, SSH, web servers, Chromium, and Firefox browsers, to name a few. Thousands of developers from different countries work on these projects, and it is nearly impossible to inject malicious code or a backdoor when you are watched 24/7. Involuntary errors are also detected in the same way, which makes these “free open-source” projects extremely stable and reliable.

## A Realistic Perspective on Security

While we advocate for the security benefits of open-source, we acknowledge that no system is impervious. But in discussing security, it's worth noting that attacks on infrastructure, i.e., the service environment, are probably more frequent and can be much more devastating. Every web server constantly faces attempts to guess the root password, scan its open ports, etc. If a web server or database is not properly protected by a firewall, or if the sysadmin’s password is something as weak as 'admin123' (which happens more often than you would think), then no matter how good and clean your site code is, vulnerabilities may exist.

In conclusion, PassHub.net’s open-source nature is not just a feature; it's a fundamental aspect of our strategy. By embracing transparency, encouraging collaboration, and learning from the broader open-source community. Through these practices, we build a more secure environment for our users.

## Summary: 

Discover how PassHub.net addresses security concerns by embracing transparency and collaboration. Learn why showing the code internals enhances trust and security, contrasting with the pitfalls of closed-source systems. How open-source practices, peer review, and the use of widely-accepted cryptographic algorithms contribute to robust security. Plus, get insights into the broader open-source ecosystem's role in ensuring reliability and mitigating risks like backdoors
