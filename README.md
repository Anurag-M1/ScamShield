# ScamShield 🛡️
> **Real-Time Client-Side Phishing, Scam & Extortion Intelligence Engine**  
> *Built for Cybersecurity Hackathon 2026 (Phishing & Online Safety Track)*

[![Privacy: 100% Client-Side](https://img.shields.io/badge/Privacy-100%25%20In--Browser-10b981.svg)](#privacy-guarantee)
[![Dependencies: Zero](https://img.shields.io/badge/Dependencies-Zero%20(Vanilla%20HTML%2FCSS%2FJS)-06b6d4.svg)](#architecture)
[![Deploy: Static Ready](https://img.shields.io/badge/Deploy-GitHub%20Pages%20%7C%20Netlify%20%7C%20Vercel-6366f1.svg)](#how-to-run)

---

## 📌 What It Is
**ScamShield** is an instant, offline cybersecurity triage tool designed to protect users from modern social engineering attacks, deceptive messages, and phishing URLs. 

Users can paste any suspicious SMS, WhatsApp message, email excerpt, or link. ScamShield immediately returns:
1. **Dynamic Risk Score (0–100)** with an animated cyber gauge and triage verdict (**Safe**, **Suspicious**, or **Likely Scam**).
2. **In-Text Annotated X-Ray**: Every red flag is highlighted directly inside the original message with color-coded severity tags (`[CRITICAL]`, `[HIGH]`, `[MEDIUM]`).
3. **Plain-English Explanations**: Details *why* each indicator is dangerous and what psychological manipulation trick the scammer is using.
4. **Actionable Checklist**: Interactive, step-by-step guidance on what to do immediately (freeze bank cards, report to authorities, block sender, do not share OTP).
5. **One-Click Triage Report**: Copies a structured security report to the clipboard for sharing with victims, IT helpdesks, or police portals.

---

## ⚡ 6 Built-In One-Click Demo Scenarios
ScamShield includes 6 pre-configured test scenarios to demonstrate immediate detection across different scam vectors:
1. **🏦 Fake Bank KYC Notice**: Phishing SMS threatening account suspension within 24h, requesting NetBanking password & OTP, hosted on a fake `.xyz` domain. *(Score: 100/100 • Likely Scam)*
2. **📦 Courier Fee Hold**: Impersonates USPS/FedEx with an urgent unpaid customs fee of $1.99 and an obfuscated `bit.ly` shortened link. *(Score: 100/100 • Likely Scam)*
3. **🎁 Mega Lottery Win**: Advance-fee fraud promising a $1.5M Coca-Cola prize, demanding ATM PIN and bank account details. *(Score: 93/100 • Likely Scam)*
4. **🚨 Digital Arrest Extortion Threat**: Impersonates Police/Narcotics Control Bureau with a bogus arrest warrant, demanding video call connection and AnyDesk remote app installation. *(Score: 100/100 • Likely Scam)*
5. **🪪 Typosquatted Login URL**: Phishing alert linking to a lookalike typosquatted domain (`paypa1-security-verification.top`) to harvest credentials. *(Score: 100/100 • Likely Scam)*
6. **☕ Safe Message**: Normal lunch invitation with zero red flags. *(Score: 0/100 • Safe)*

---

## 🧠 How the Detection Engine Works
ScamShield runs a deterministic, multi-channel heuristic detection engine in pure JavaScript:

### 1. Message Signals (Social Engineering & Coercion)
- **Urgency & Artificial Time Pressure**: Identifies coercive phrases (`"within 24 hours"`, `"account will be blocked"`, `"act now"`, `"final notice"`).
- **Credential & Financial Harvesting**: Detects requests for OTP, ATM PIN, CVV, passwords, card numbers, Aadhaar, or SSN.
- **Fake Compliance & KYC Baits**: Flags fake account freeze alerts, KYC pending notices, tax refunds, and overdue utility disconnection lures.
- **Prize & High-Yield Investment Traps**: Detects unsolicited lottery wins, crypto airdrops, and "task job" scams.
- **Digital Arrest Extortion**: Flags fake police warrants, customs drug seizures, and intimidation tactics.
- **Remote Access Exploitation**: Flags prompts to install remote management software (`AnyDesk`, `TeamViewer`, `QuickSupport`) or download unofficial Android `.apk` files.
- **Brand & Institutional Impersonation**: Detects unauthorized references to major banks, courier firms, and tech platforms.

### 2. URL & Domain Forensics
- **Typosquatting Engine**: Evaluates domain tokens against a registry of 30+ high-profile brands (PayPal, Apple, Amazon, HDFC, SBI, Chase, FedEx, etc.) using **Levenshtein distance** and character substitution maps (`0 -> o`, `1 -> l`, `vv -> w`, `rn -> m`).
- **High-Abuse TLDs**: Flags domains hosted on cheap, disposable top-level domains (`.xyz`, `.top`, `.click`, `.zip`, `.cam`, `.sbs`, etc.).
- **URL Obfuscation & Shorteners**: Detects link shortening services (`bit.ly`, `tinyurl.com`, `t.co`) that conceal true destinations.
- **Homoglyph / Punycode (IDN Spoofing)**: Detects internationalized character sets (Cyrillic/Greek lookalikes) designed to visually deceive victims.
- **Raw IP Address & Deceptive Authority**: Flags links pointing to numerical IP addresses or using the `@` symbol trick.
- **Protocol Security**: Flags plain, unencrypted `http://` links attempting credential verification.

---

## 🔒 Privacy Guarantee
- **100% Client-Side**: All analysis executes entirely in the user's browser memory.
- **Zero Network Calls**: No API keys, no telemetry, no tracking scripts, no external fonts or CDN dependencies.
- **Double-Click Executable**: Works offline via the `file://` protocol.

---

## 🚀 How to Run & Deploy

### Run Locally (Instant)
Just double-click `index.html` in any web browser (Chrome, Safari, Firefox, Edge).  
No `npm install`, no build tools, and no server required.

### Deploy to Web
Deploy in seconds to any static hosting provider:
- **GitHub Pages**: Push `index.html` to a repository and enable GitHub Pages under Settings > Pages.
- **Netlify Drop**: Drag and drop the folder directly onto [app.netlify.com/drop](https://app.netlify.com/drop).
- **Vercel**: Run `npx vercel` or import the repository.

---

## ⚠️ Limitations
- Heuristic engines evaluate structural and linguistic indicators; highly bespoke, context-specific spear-phishing without obvious urgency or links may score lower.
- URL analysis inspects domain syntax, entropy, and reputation rules, but does not perform server-side web scraping or live sandbox detonation of malware payloads.

---

## 🔮 Future Work & Roadmap
1. **On-Device Machine Learning Classifier**: Integrate a quantized ONNX / WebAssembly transformer model (e.g. MobileBERT / DistilBERT fine-tuned on phishing corpora) for nuanced contextual classification.
2. **Browser Extension**: Real-time background scanning for webmail (Gmail, Outlook), social media, and web browsing.
3. **WhatsApp / Telegram Safety Bot**: Send suspicious forwarded messages to a bot endpoint for instant scam reports.
4. **QR Code Scanner**: In-browser camera decoding to inspect embedded phishing URLs inside physical letters and utility bills.

---

## 📝 License
MIT License • Open source for hackathon presentation and cybersecurity awareness.
