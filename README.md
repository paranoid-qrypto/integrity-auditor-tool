# Paranoid Qrypto: Integrity Auditor Tool

![Apache 2.0 License](https://img.shields.io/badge/License-Apache_2.0-ffd700.svg)
![Version](https://img.shields.io/badge/Version-1.0.0-informational.svg)
![Maintained](https://img.shields.io/badge/Maintained-Yes-green.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

<p align="center">
  <img src="docs/logo.png" alt="Paranoid Qrypto Logo" width="128">
</p>

A 100% client-side, single-file HTML tool for securely auditing code and verifying file integrity. This tool provides side-by-side code comparison and a comprehensive file hash calculator/verifier (MD5, SHA-256, SHA-512).

---

## Security-First Philosophy

This tool was built with a "paranoid" mindset, prioritizing security and transparency above all else.

*   **100% Client-Side:** All operations happen directly in your web browser. No files, code, or data are ever sent to any server. Your data remains on your machine, always.
*   **Works Completely Offline:** The tool is a single HTML file with no external dependencies. You can download it and run it on a completely air-gapped computer for maximum security.
*   **Fully Auditable:** The entire source code is contained within a single, human-readable file. There are no hidden packages or compiled code. What you see is what you get.

## Cross-Platform Compatibility

As a self-contained HTML application, the Integrity Auditor Tool runs on any modern device with a standards-compliant web browser.

*   **Desktop:** Windows, macOS (Intel), macOS (Apple Silicon), Linux
*   **Mobile:** Android OS, iOS / iPadOS
*   **Other devices:** E.g. Chromebook, Raspberry Pi, etc.
*   **Supported Browsers:** Works on all modern browsers, including Chrome, Firefox, Safari, Edge, and Brave.

### Requirements

*   **JavaScript must be enabled** in your browser for the tool to function.
*   The tool must be served over **HTTPS or from `localhost`** for the Web Crypto API (SHA-256/512) to be available.

### Offline Capabilities

The `integrity-auditor-tool.html` file is designed to be fully portable and functional without an internet connection.

**All functions are available OFFLINE:**
*   ✅ **Code Comparison** (Strict, Normalized, and Whitespace-Removed)
*   ✅ **File Hash Calculation** (MD5, SHA-256, SHA-512)
*   ✅ **File Hash Verification** (against provided checksums)
*   ✅ **Save Results** to a local text file

---

## Key Features

### Code Comparison Tool
*   **Side-by-Side Input:** Paste text or upload files into two panels for direct comparison.
*   **Multi-Level Analysis:**
    *   **Strict Comparison:** Verifies if the content is bit-for-bit identical using SHA-256 hashes.
    *   **Normalized Comparison:** Checks for identity after standardizing line endings and trimming whitespace.
    *   **Whitespace-Removed Comparison:** Checks for identity after removing all whitespace characters.
*   **Stringified View:** Inspect the whitespace-removed versions of your inputs to manually spot differences.

### File Hash Verifier Tool
*   **Comprehensive Hash Calculation:** Calculate **MD5, SHA-256, and SHA-512** hashes for one or more files simultaneously.
*   **Flexible Verification:**
    *   Verify a single file by pasting its expected hash(es).
    *   Verify multiple files at once by pasting a checksum file's content (e.g., `sha256sums.txt`).
*   **Clear Results:** Get an easy-to-read summary of which files passed or failed verification.
*   **Saveable Reports:** Export the calculation or verification results to a timestamped `.txt` file for your records.

---

## How to Use

### To Compare Code or Text
1.  Open the `integrity-auditor-tool.html` file and select the **"Code Comparison"** tab.
2.  Paste your content into the "Input 1" and "Input 2" boxes, or use the "Upload File" buttons.
3.  Click **"Compare Content"**.
4.  Analyze the results in the "Comparison Analysis" section that appears.

### To Verify File Hashes
1.  Select the **"File Hash Verifier"** tab.
2.  Click **"Select File(s)"** to choose the file(s) you want to analyze.
3.  **To Calculate:** Simply click **"Calculate Hashes"**.
4.  **To Verify:**
    *   Provide the expected hash(es) in the "Verify File Integrity" section on the right.
    *   Click **"Verify Selected Files"**.
5.  Review the results, which will show a clear "Match" or "Mismatch" status for each hash.

---

## Dependencies & Verification

This tool is designed to be a secure, self-contained HTML file. The following libraries are used.

### 1. Web Crypto API (Native Browser API)
*   **Purpose:** Used for all secure hash calculations (**SHA-256, SHA-512**).
*   **Source:** This is a standard, built-in browser API. No third-party code is downloaded.
*   **Note:** This API is only available in secure contexts (HTTPS or localhost).

### 2. js-md5
*   **Version:** `0.7.3`
*   **Purpose:** A lightweight library for calculating **MD5** hashes, included for compatibility with older checksums. The code is embedded directly in the HTML file.
*   **Source of Truth (NPM):** [https://www.npmjs.com/package/js-md5/v/0.7.3](https://www.npmjs.com/package/js-md5/v/0.7.3)
*   **Direct Download Link:** [https://cdn.jsdelivr.net/npm/js-md5@0.7.3/src/md5.js](https://cdn.jsdelivr.net/npm/js-md5@0.7.3/src/md5.js)
*   **SHA-256 Hash of Embedded Script:** `c690299cd533422a8773ed03a83a6c92404d950e460481dbbc512ba451bbb857`

---

## License

This project is licensed under the **Apache License 2.0**. Please see the `LICENSE` file for full details. A `NOTICE` file is also included for attribution purposes.

## Disclaimer

This tool is provided "AS IS", WITHOUT WARRANTY OF ANY KIND, either express or implied. The user assumes all risks associated with its use. Always verify critical information from multiple sources when possible.

## Bug Reports & Feedback

If you find a bug or have a feature request, please open an issue on the [GitHub Issues page](https://github.com/paranoid-qrypto/integrity-auditor-tool/issues).

## Developed and provided by Paranoid Qrypto

[https://paranoidqrypto.com/](https://paranoidqrypto.com)
© 2025 Paranoid Qrypto
