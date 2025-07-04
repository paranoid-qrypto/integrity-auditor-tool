# Paranoid Qrypto: Integrity Auditor Tool

![Apache 2.0 License](https://img.shields.io/badge/License-Apache_2.0-ffd700.svg)
![Version](https://img.shields.io/badge/Version-1.0.0-informational.svg)
![Maintained](https://img.shields.io/badge/Maintained-Yes-green.svg)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

<p align="center">
  <a href="https://paranoidqrypto.com/" target="_blank" rel="noopener noreferrer">
    <img src="docs/logo.png" alt="Paranoid Qrypto Logo" width="128">
  </a>
</p>

A 100% client-side, single-file HTML tool for securely auditing code and verifying file integrity. This tool provides side-by-side code comparison and a comprehensive file hash calculator/verifier (MD5, SHA-256, SHA-512).

---

## Security-First Philosophy

This tool was built with a "paranoid" mindset, prioritizing security and transparency above all else.

*   **100% Client-Side:** All operations happen directly in your web browser. No files, code, or data are ever sent to any server. Your data remains on your machine, always.
*   **Works Completely Offline:** The tool is designed to be fully functional without an internet connection. You can download it and run it on a completely air-gapped computer for maximum security.
*   **Fully Auditable:** The entire source code is contained within a single, human-readable file. There are no hidden packages or compiled code. What you see is what you get.

## Understanding the Project Structure

This repository contains two primary HTML files to serve different use cases:

1.  **`index.html` (for GitHub Pages & Online Use)**
    *   This file is a **completely self-contained application**. All necessary JavaScript (like the `md5.js` library) is embedded directly within the file.
    *   **Purpose:** This ensures that the tool can be hosted on GitHub Pages and run as a true single-file application. It's the file you use when accessing the tool via the web URL.

2.  **`integrity-auditor-tool.html` (for Local Use & Development)**
    *   This file is structured for easier development. It links to external JavaScript files located in the `/js/` directory (e.g., `<script src="js/md5.js"></script>`).
    *   **Purpose:** This is the recommended file to use when you have downloaded the entire repository to your local machine. It keeps the code cleaner and easier to manage.

## How to Use

There are two ways to use the Integrity Auditor Tool:

### 1. Online (Recommended for Quick Access)

Simply visit the live version hosted on GitHub Pages. No download is required.

**[https://paranoid-qrypto.github.io/integrity-auditor-tool/](https://paranoid-qrypto.github.io/integrity-auditor-tool/)**

### 2. Offline (Recommended for Maximum Security)

1.  Download the repository to your local machine (either via `git clone` or by downloading the ZIP file).
2.  Disconnect from the internet (optional, for a true air-gapped environment).
3.  Open the **`integrity-auditor-tool.html`** file in your web browser.

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

## Dependencies & Verification

This tool relies on two primary JavaScript sources for its functionality.

### 1. Web Crypto API (Native Browser API)
*   **Purpose:** Used for all secure hash calculations (**SHA-256, SHA-512**).
*   **Source:** This is a standard, built-in browser API. No third-party code is downloaded.
*   **Note:** This API is only available in secure contexts (HTTPS or localhost).

### 2. js-md5
*   **Version:** `0.7.3`
*   **Purpose:** A lightweight library for calculating **MD5** hashes, included for compatibility with older checksums.
*   **Source of Truth (NPM):** [https://www.npmjs.com/package/js-md5/v/0.7.3](https://www.npmjs.com/package/js-md5/v/0.7.3)
*   **Direct Download Link:** [https://cdn.jsdelivr.net/npm/js-md5@0.7.3/src/md5.js](https://cdn.jsdelivr.net/npm/js-md5@0.7.3/src/md5.js)
*   **SHA-256 Hash of `js/md5.js`:** `c690299cd533422a8773ed03a83a6c92404d950e460481dbbc512ba451bbb857`
*   **Note:** The code in `js/md5.js` and the code embedded in `index.html` should both match this hash.

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
