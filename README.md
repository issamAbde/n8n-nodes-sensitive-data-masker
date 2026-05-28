# n8n-nodes-sensitive-data-masker

This is an n8n community node that allows you to easily mask, redact, and anonymize sensitive data (PII) like Emails, IBANs, and Phone numbers within your workflows. Ensure GDPR compliance and protect user privacy before sending data to third-party APIs or LLMs.

[Key Features](#key-features) •
[Installation](#installation) •
[Usage](#usage) •
[Technical Highlights](#technical-highlights)

---

## Why use this node?

When building automation workflows—especially those integrating AI, LLMs, or external analytics—handling raw personal data poses a major security and compliance risk.

The **Sensitive Data Masker** acts as an automated privacy guard. It scans your data fields and applies customizable masking patterns, ensuring that sensitive information never leaves your secure infrastructure un-anonymized.

## Key Features

- 🛡️ **PII Protection:** Native support for masking common sensitive patterns (Emails, IBANs, Phone numbers).
- 🎛️ **Total Control:** Mask specific JSON fields, or define custom text patterns using custom regular expressions (Regex).
- 🔄 **Deep Recursive Scan:** Automatically traverses nested JSON structures to protect data at every level.
- ⚡ **Security-First:** Built following n8n's strict security guidelines to prevent Prototype Pollution and Regular Expression Denial of Service (ReDoS).

---

## Installation

### For n8n Users (Community Node Registry)

You can easily install this node directly from your n8n instance:

1. Open your n8n instance in your browser.
2. Go to **Settings > Community Nodes**.
3. Click on **Install a community node**.
4. Enter the npm package name: `n8n-nodes-sensitive-data-masker`
5. Agree to the risks and click **Install**.

## Usage

Once installed, the Sensitive Data Masker node will appear in your n8n node selector.

#### Configuration Parameters

Value to Mask: Select or map the incoming field data (={{ $json.myField }}) that contains the text or JSON object you want to anonymize.

Masking Rule: Choose how you want to mask the data:

Predefined Rule: Select from quick presets like Email, IBAN, or Phone Number.

Custom Rule: Define your own replacement character (e.g., \* or [MASKED]) or input a custom Regex pattern.

### Input / Output Example

### Incoming Data (Input):

JSON
{
"user": {
"name": "Issam",
"email": "test.issam@gmail.com",
"phone": "0612345678"
}
}
Processed Data (Output):

JSON
{
"user": {
"name": "Issam",
"email": "[MASKED]",
"phone": "[MASKED]"
}
}

## Technical Highlights

Language: Written completely in TypeScript.

Performance: Optimized recursive traversal algorithm for handling large JSON payloads without blocking the Node.js event loop.

Reliability: Built and structured to be fully compatible with the core n8n architecture.

License
MIT
