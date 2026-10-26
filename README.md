# Serren Luxx's Portable Text Vault

A simple, browser-based tool for encrypting text into a downloadable file and decrypting it whenever you need to read it again.

No account required. No software installation required. Just open the page, enter your text, choose a master password, and download your encrypted file.

## What Can It Do?

- **Encrypt text:** Protect private notes, personal information, or other text you want to keep confidential.
- **Download encrypted files:** Save your encrypted text as a `.txt` file that you can store on your computer, back up, or transfer elsewhere.
- **Decrypt files:** Open a previously encrypted vault file with the correct master password.
- **Copy decrypted text:** Copy the recovered text to your clipboard with one click.
- **Work locally:** Encryption and decryption are performed in your browser. The tool's code does not intentionally send your text or password to a server.
- **Open older vault files:** The current version supports files created by the original version of this tool.

## How to Use It

### 1. Encrypt Text

1. Open [Serren Luxx's Portable Text Vault](https://serrenluxx.github.io/portable-text-vault/).
2. Enter or paste the text you want to protect into the **Text to protect** box.
3. Enter a master password containing at least 14 characters.
4. Click **Encrypt and download vault file**.
5. Save the downloaded `serren-vault.txt` file somewhere safe.

Your text is encrypted before the file is downloaded. Keep the encrypted file and your master password separate.

### 2. Decrypt an Encrypted File

1. Open the vault webpage.
2. Under **Decrypt a vault file**, select the encrypted file you want to open.
3. Enter the master password used when that file was encrypted.
4. Click **Decrypt and show text**.
5. Once decryption succeeds, your original text will appear in the text box.
6. Click **Copy decrypted text** if you want to copy it elsewhere.

When you are finished, close the page or clear the displayed text from the text box.

### 3. Use It Offline

You can download the HTML file from this repository and keep a copy on your computer.

To download it, open `index.html` in the repository, click **Raw**, and save the page as an HTML file. You can then open the saved file in a compatible browser.

A current browser with Web Crypto support is required. If the browser reports that cryptographic features are unavailable, try opening the hosted HTTPS version instead.

## Encryption Details

This tool uses standard browser cryptography APIs.

- **Encryption:** AES-256-GCM
- **Password-based key derivation:** PBKDF2-HMAC-SHA-256
- **Key-derivation iterations for new files:** 600,000
- **Random salt:** 16 bytes
- **Random nonce (IV):** 12 bytes
- **Minimum master password length for new files:** 14 characters

AES-GCM provides both confidentiality and integrity protection. PBKDF2 makes password guessing more computationally expensive by requiring repeated calculations to derive the encryption key.

These settings do not guarantee absolute security. The strength of your master password remains important.

## Important Things to Know

**Your master password cannot be recovered.**

There is no password-reset feature or recovery service. If you lose your master password, you may permanently lose access to the encrypted text.

**Choose a strong, unique master password.**

A long passphrase made from several unrelated words is a practical starting point. Avoid passwords that are easy to guess or that you already use for other accounts.

**Keep backups of your encrypted files.**

The tool downloads your encrypted text to your device. It does not maintain an online copy for you. If you lose the file, the encrypted content may be lost.

**Encryption does not protect everything around the file.**

Anyone who obtains your master password may be able to decrypt your file. Malware, compromised devices, browser extensions, or someone accessing your computer may also put your information at risk.

**This is not a dedicated post-quantum cryptography system.**

The tool uses AES-256-GCM, which is considered a strong encryption algorithm, but it does not implement a dedicated post-quantum cryptographic scheme. No claim is made that it is immune to every possible future attack.

**Check important files before relying on them.**

Test encryption and decryption with non-sensitive sample text first. Keep your original files until you have confirmed that the encrypted files can be opened successfully.

## Privacy

The cryptographic operations are performed locally in your browser. This tool does not include a server-side service for receiving or storing the text you encrypt.

If you use the hosted webpage, your browser still needs to download the webpage from its hosting provider. The hosting provider may process ordinary website access information, such as request logs. Avoid using a device you do not trust for sensitive information.

## Open Source

You can inspect the HTML and JavaScript in this repository to see how the tool works.

- **Website:** [Serren Luxx's Portable Text Vault](https://serrenluxx.github.io/portable-text-vault/)
- **Source code:** Browse the files in this repository.
- **Creator:** [Serren Luxx](https://serrenluxx.com/)

This project is provided as a convenient personal text-encryption tool. Use it responsibly, keep your master password safe, and always maintain backups of important data.
