# 📧 Phishing Email Analysis - Task 2 (Cybersecurity Internship)

## 📝 Objective
This task aims to identify phishing characteristics in a suspicious email and build awareness about email threats, spoofing, header analysis, and social engineering tactics.

---

## 🔧 Tools Used
- Sample phishing email (custom-created)
- [MXToolbox Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)
- Browser (to hover and inspect links)
- GitHub (for documentation & submission)

---

## 📩 Sample Phishing Email

*File:* sample_email.txt


From: PayPal Security support@paypa1.com To: you@example.com Subject: Urgent Action Required: Account Suspension Notice

Dear user,

We have noticed suspicious activity in your PayPal account. If you do not verify your identity within 24 hours, your account will be permanently suspended.

Please click the link below to verify your account immediately:

👉 https://www.paypal.com.verify-security-alert.com

Failure to act will result in complete suspension of your PayPal account and may affect linked bank accounts.

Thank you for your prompt attention.

Sincerely,
PayPal Verification Team
support@paypa1.com

---

## 📤 Sample Email Header

*File:* header.txt

Return-Path: support@paypa1.com Received: from badhost.ru ([45.67.89.123]) by mail.fakehost.net; Authentication-Results: spf=fail smtp.mailfrom=paypa1.com; dkim=fail (signature mismatch) From: "PayPal Security" support@paypa1.com To: you@example.com Subject: Urgent Action Required: Account Suspension Notice Date: Tue, 6 Aug 2025 10:15:00 +0000 Message-ID: 9348234@badhost.ru

---

## 🔍 Step-by-Step Analysis

### ⿡ Sender’s Email Address
- Appears to be from: support@paypa1.com
- Domain is suspicious and not the real PayPal domain (paypal.com)
- This is classic *email spoofing*

---

### ⿢ Email Header Analysis

*Tool Used:* [MXToolbox Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)

*Key Findings:*
- *Sender IP:* 45.67.89.123 — not belonging to PayPal
- *SPF Check:* ❌ FAIL
- *DKIM Check:* ❌ FAIL
- *Return Path:* support@paypa1.com (spoofed)
- *Hostname:* badhost.ru
- *Conclusion:* This email is highly suspicious and likely spoofed

---

### ⿣ Suspicious Links
- Text: https://www.paypal.com.verify-security-alert.com
- Appears genuine but is a *malicious domain*
- Uses a fake subdomain to mimic PayPal

---

### ⿤ Urgent Language
- “Verify your account within 24 hours”
- “Failure to act will result in account suspension”
- Designed to create fear and rush the user

---

### ⿥ Generic Greeting
- “Dear user” instead of personalized name
- Legitimate companies usually greet you by name

---

### ⿦ Social Engineering Tactics
- Creates a sense of panic
- Uses fear to force the user to click a malicious link

---

## ✅ Summary of Phishing Indicators

| Indicator                    | Present? | Explanation |
|-----------------------------|----------|-------------|
| Spoofed Sender Email        | ✅        | support@paypa1.com is fake |
| Suspicious Links            | ✅        | Looks like PayPal but redirects to phishing site |
| SPF / DKIM Failures         | ✅        | Header analysis shows failure |
| Urgent Language             | ✅        | Pressures user to act fast |
| Generic Greeting            | ✅        | Not personalized |
| Social Engineering          | ✅        | Fear-based manipulation |

---

## 📁 Repository Contents

phishing-email-analysis-task2/ 
├── README.md 
├── sample_email.txt
├── header.txt 
├── screenshots/