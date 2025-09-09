# GPG Cheat Sheet

GNU Privacy Guard (GPG) commands for encryption, decryption, and key management.

---

## Table of Contents
- [Key Management](#key-management)
- [Import/Export Keys](#importexport-keys)
- [Encryption/Decryption](#encryptiondecryption)
- [Key Information](#key-information)
- [Advanced Operations](#advanced-operations)

---

## Key Management

| Command | Description | Example |
|---------|-------------|---------|
| `gpg --gen-key` | Create a new key pair | `gpg --gen-key` |
| `gpg --delete-key "Name"` | Delete public key | `gpg --delete-key "John Doe"` |
| `gpg --delete-secret-key "Name"` | Delete private key | `gpg --delete-secret-key "John Doe"` |

*Note: Must delete private key before deleting associated public key*

## Import/Export Keys

| Command | Description | Example |
|---------|-------------|---------|
| `gpg --export -a "Name" > file.key` | Export public key | `gpg --export -a "John Doe" > public.key` |
| `gpg --export-secret-key -a "Name" > file.key` | Export private key | `gpg --export-secret-key -a "John Doe" > private.key` |
| `gpg --import keyfile` | Import public key | `gpg --import public.key` |
| `gpg --import keyfile` | Import private key | `gpg --import private.key` |

## Key Information

| Command | Description | Example |
|---------|-------------|---------|
| `gpg --list-keys` | List public keys | `gpg --list-keys` |
| `gpg --list-secret-keys` | List private keys | `gpg --list-secret-keys` |
| `gpg --fingerprint` | Show key fingerprints | `gpg --fingerprint > fingerprint` |

## Encryption/Decryption

| Command | Description | Example |
|---------|-------------|---------|
| `gpg -e -u "Sender" -r "Recipient" file` | Encrypt file | `gpg -e -u "John" -r "Jane" document.txt` |
| `gpg -d file.gpg` | Decrypt to stdout | `gpg -d document.txt.gpg` |
| `gpg -o output -d file.gpg` | Decrypt to file | `gpg -o document.txt -d document.txt.gpg` |
| `gpg -c file` | Symmetric encryption | `gpg -c document.txt` |

*Note: Original files are preserved after encryption*

## Advanced Operations

| Command | Description | Example |
|---------|-------------|---------|
| `gpg --edit-key "Name"` | Edit key properties | `gpg --edit-key "John Doe"` |
| `gpg --gen-revoke "Name"` | Generate revocation certificate | `gpg --gen-revoke "John Doe"` |

## Tips & Tricks

- **Self-encryption**: Encrypt files for yourself using your own key as recipient
- **Key sharing**: Export/import keys to sync across multiple computers
- **Group keys**: Share a single key pair among team members
- **Security**: Never share private keys via unencrypted channels

---

## Resources
- [GPG Manual](https://www.gnupg.org/gph/en/manual.html)
- [GPG Documentation](https://www.gnupg.org/documentation/)

---
*Originally compiled from various sources. Contributions welcome!*
