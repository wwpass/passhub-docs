---
sidebar_label: "Password strength"
sidebar_position: 65
---

# Password Strength

_January 2022_

PassHub considers a password to be weak if it is shorter than 8 characters or it is on the list of [the most frequently used passwords](https://en.wikipedia.org/wiki/List_of_the_most_common_passwords).

PassHub follows the latest [NIST 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html#memsecret) document on password security. The National Institute of Standards and Technology (NIST) is one of the most authoritative and reputable sources of cybersecurity recommendations.

NIST password requirements are as follows:

- Minimal length of 8 symbols; in some special cases even 6-digit sequences may be enough.

- User passwords should be checked against the black list of the most frequently used passwords, say, “12345678”, “administrator”, “iloveyou”, “passw0rd”, etc.

- Spaces are allowed in passwords, with consecutive spaces counted as a single character.

Basically, that is all. There are no requirements for upper/lowercase letters, digits, or special symbols. There is also no suggestion to periodically change passwords.

Why are NIST requirements so relaxed compared to what we often see?

_Your password should include lower- and upper-case letters, numbers, and special symbols, be at least 10 characters long, and periodically changed._

Initially, the only threat model taken into account was password guessing or brute force attack. In real life, more effective ways exist to steal a user's password.

Alex Weinert, Director of Identity Security at Microsoft, shares their team experience in the blog post [“Your Pa$$word doesn't matter”](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984).

They identified the main types of attack as:

- Password reuse: Using the same password on many sites, and one compromised account turns into several.
- Password spraying: When a hacker has a list of usernames, and attempts the same password from the top ten (or even top two) most-used list on each account.
- Phishing

Other attacks, at a lower frequency, include:

- Keystroke logging
- Local discovery
- Brute force (note: in the online world brute force attacks are hardly possible at all. Every attempt takes a considerable amount of time. A properly-configured network detects successive fault attempts and blacklists that IP. Provided the password is not "123456", "passw0rd" or another from the first ten most used list, the password will not be cracked that way.)

Hence, the complexity of the password does not matter at the end of the day (excluding the top ten most frequently used).

Today the average user has more than 100 accounts. The requirement to have a unique password for each site makes it impossible to know all the passwords by heart. Passwords are no longer a “memorized Secret”. Users write them on paper, store them in a file, or, best of all, keep them in a password manager.

With password managers, it is quite natural to use the internal random password generator to get new passwords. By default, the PassHub generator produces 12 symbol length passwords with upper- and lowercase letters, digits, and special symbols to fit even the most exotic requirements of some service providers.

Still, there are some special cases when the randomly generated long passwords are hardly usable.
First is a password for your computer. There is no way to autofill or even copy/paste a pasword before the computer starts. That is one case when you need to memorize the password.

Another example is a password for your password manager—if it is based on a login/password authentication. It might be not so critical for local applications like KeePass, but online password managers need special attention. Password manager security should now be of major concern, with multifactor authentication as a mandatory feature, not a premium plan option.

PassHub does not use login/password authentication at all. Instead, it is based on WWPass multifactor authentication (MFA). Not only does WWPass MFA provide a higher level of security, but it also generates a client-side encryption key for user data. The key is not known to WWPass itself and becomes available to the browser as a result of authentication only. The key has full 256-bit entropy, and it is not derived from the password with PBKDF2 or Argon2d functions.

### Summary

A password's security is not so much its length or complexity. What really matters is:

- A properly-built attack detection system on the verifier's side
- Use of password managers
- Multi-factor authentication
