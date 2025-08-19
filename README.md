# SoSafeChecker

SoSafe will send test phishing emails to test users on their awareness of phishing emails. This tool takes all the guesswork out of it.

‼️ THIS DOES NOT CHECK IF AN EMAIL IS PHISHING OR NOT. ‼️

‼️ THIS TOOL WILL GREEN LIGHT ACTUAL PHISHING EMAILS. ‼️

This ONLY tests if the email is linking to a domain controlled by SoSafe, which all their test phishing emails do.

## How it works

SoSafe controls a number of domains that are similar to what malicious phishing attackers would use in their attacks (eg: com-c0m.net). However, the one thing these all have in common (as of time of writing) is that they include a TXT domain record at the root level: `"v=spf1 include:spf.sosafe.de -all"`. This is a Sender Policy Framework (SPF) record, which is used in mail routing in ways that are not important here.

This tool extracts all URLs from the email and queries [Google's public DNS provider](https://dns.google) to see if this TXT record is present. If it is, then the email must be from SoSafe. Simple as.

## Attribution

Favicon is credited to [Freepik on Flaticon.com](https://www.flaticon.com/free-icon/magnifying-glass_2015046)