# Attacker vs Defender — Personal Email Account

## The system
My personal email account is my primary digital identity, used daily to manage personal communications, school platforms, and online service logins. It matters to me because compromising this account would give an attacker access to sensitive personal information and allow them to reset passwords for almost all my other online services.

## Attacker view
An attacker could attempt a spear-phishing attack by sending a convincing email that looks like an urgent notification from my school or email provider. The email would contain a link to a fake login page designed to capture my credentials when I try to sign in. If the attack succeeds, the attacker gains full access to my inbox, my sent emails, and the ability to initiate password resets for connected accounts like social media or online banking.

## Defender view
To defend against this, I can enable Multi-Factor Authentication (MFA) using an authenticator app on my mobile phone. When MFA is active, entering the correct password is not enough; a time-sensitive verification code from my physical phone is also required to log in. This forces an attacker to either physically steal my phone or execute a far more complex adversary-in-the-middle attack, making a simple credential-harvesting link ineffective. However, this defense does not protect against malware already running on my device that could hijack an active session after I have authenticated.

## CIA angle
This scenario primarily threatens **Confidentiality**, as an unauthorized person gains access to private communications and personal data. Secondarily, it threatens **Integrity**, because the attacker could send fraudulent emails from my account or alter my account settings.

## What I'm changing this week
This week, I am switching my multi-factor authentication method from SMS-based codes to an authenticator app (such as Google Authenticator or Bitwarden). While I already had MFA enabled via SMS, moving to an app eliminates the risk of SIM-swapping attacks and makes my account significantly more secure against credential theft.
