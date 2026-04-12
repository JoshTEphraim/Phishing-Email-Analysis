# FUTURE_CS_02
# Phishing Email Detection & Awareness Report

A real-world phishing email analysis project completed as part of a SOC Analyst awareness exercise. Two live phishing samples were collected, analyzed using industry-standard tools, and documented in a client-ready report.

---

## Project Overview

Phishing is one of the most common entry points for cyber attacks in organizations. This project simulates the work of a SOC analyst performing phishing triage - from collecting samples to documenting findings and writing prevention guidelines for employees.

---

## Samples Analyzed

| Sample | Impersonated Brand | Attack Type | Risk |
|--------|-------------------|-------------|------|
| Sample 1 | Lido DAO | Crypto wallet drain via fake airdrop | HIGH - PHISHING |
| Sample 2 | Microsoft | Account impersonation via fear lure | HIGH - PHISHING |

Both samples were sourced from [rf-peixoto/phishing_pot](https://github.com/rf-peixoto/phishing_pot), a public honeypot repository of real phishing emails captured in the wild.

---

## Tools Used

| Tool | Purpose |
|------|---------|
| [Mozilla Thunderbird](https://www.thunderbird.net) | Safely render .eml files as the victim would see them |
| [Google Admin Toolbox - Message Header Analyzer](https://toolbox.googleapps.com/apps/messageheader/) | Visualize email routing path and inspect SPF, DKIM, DMARC |
| [MXToolbox](https://mxtoolbox.com/EmailHeaders.aspx) | Alternative header analysis and domain lookup |

---

## Analysis Approach

Each phishing email was analyzed following a five-step triage process:

1. **Sample Collection** - Downloaded real .eml files from a public honeypot repository
2. **Email Rendering** - Opened in Thunderbird with remote content blocked for safe viewing
3. **Header Analysis** - Submitted headers to Google Admin Toolbox to inspect authentication and mail routing
4. **Indicator Identification** - Checked sender domain, Reply-To address, embedded URLs, urgency language, and greeting
5. **Risk Classification** - Classified each email as Safe, Suspicious, or Phishing based on evidence weight

---

## Key Findings

**Sample 1 - Lido DAO Crypto Airdrop**
- Sender domain `itariannotifications.com` has no relation to `lido.fi`
- Claim button linked to `lido-airdrop.tcgprices.co.uk` - a fake wallet drain site
- Hidden HTML page title `copy_metamask` confirmed malicious intent
- SPF and DKIM passed for the attacker's own domain - not Lido's

**Sample 2 - Microsoft Account Alert**
- Sender domain `access-accsecurity.com` has no relation to `microsoft.com`
- Reply-To set to `solutionteamrecognizd03@gmail.com` - Microsoft never uses Gmail
- Report The User button emailed the attacker directly instead of Microsoft
- SPF: none, DKIM: none, DMARC: permerror - all authentication checks failed

---

## Deliverable

The full report includes:
- Analyzed phishing email examples with screenshots
- Identified indicators per sample
- Risk classification with MITRE ATT&CK mapping (T1566.002)
- Prevention guidelines and Do's and Don'ts for employees
- Response steps for users who clicked a malicious link

---

## MITRE ATT&CK Mapping

Both samples map to **T1566.002 - Spearphishing Link**, where attackers send emails containing malicious links designed to redirect victims to attacker-controlled infrastructure.

---

## Disclaimer

All phishing samples used in this project were sourced from a public honeypot repository for educational purposes only. No malicious links were clicked or interacted with during analysis. This project is purely defensive and educational in nature.

---

## Author

**[Your Name]**
SOC Analyst | CompTIA Security+ | BTL1
[LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)
