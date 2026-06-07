# DeadDrop — Encrypted File Vault

**Zero-trust encrypted container for sensitive files.**

Built by a 16-year-old self-taught developer in Iran. No tutorials. No shortcuts. Just Python, OOP, and cryptography.

---

## What It Does

DeadDrop takes your files, encrypts them with AES-256-GCM, and locks them inside a password-protected vault. Without the password, the vault reveals nothing — no filenames, no sizes, no contents.

- **Create vault** — encrypt files into a `.vault` container
- **Open vault** — decrypt and browse contents
- **Extract files** — restore original files, bit-for-bit identical
- **List contents** — view vault without decrypting files
- **Delete entries** — remove files from vault
- **Change password** — re-encrypt with new credentials

---

## Why Not ZIP?

ZIP encryption is breakable. DeadDrop uses:

| Feature | ZIP | DeadDrop |
|---------|-----|----------|
| Encryption | Sometimes AES | Always AES-256-GCM |
| Tamper detection | No | Yes |
| Password stored | As hash | Never stored |
| Wrong password | Reveals failure | Reveals nothing |
| Key derivation | Weak | PBKDF2 (500K iterations) |

---

## Tech Stack

- **Python 3.10+** — No external UI frameworks
- **pycryptodome** — AES-256-GCM, PBKDF2
- **hashlib + hmac** — Integrity verification
- **pathlib** — Cross-platform file handling
- **json** — Encrypted metadata storage
- **Custom binary format** — Designed from scratch

---

## Architecture
