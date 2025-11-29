This project follows the rights.txt protocol  
[![](https://img.shields.io/badge/rights.txt-enabled-9333ea)]()

# rights.txt — Minimal Public Rights Declaration Protocol

rights.txt is a simple, text-only file placed at the root of any website or project to publicly declare what is allowed, what is forbidden, and which licence governs the published content. All declarations must be objectively verifiable by anyone. The protocol is technology-neutral, organization-neutral, identity-neutral, and fully open.

## Specification (v0.1)

The rights.txt file must follow seven universal rules defined by the protocol:

### 1. File Location
A plain UTF-8 text file named rights.txt must exist at the root of the domain or project. It must be publicly accessible without cookies, JavaScript, authentication, or redirects, and must contain one declaration per line using the format key: value.

### 2. Rights Model
The file must declare the rights model applied to the covered content (for example: rights-model: open, restricted, or proprietary).

### 3. Allowed Usage
The file must declare which uses are explicitly allowed (for example: allowed: reuse, share, remix, non-commercial).

### 4. Forbidden Usage
The file must declare which uses are explicitly forbidden (for example: forbidden: commercial, ai-training, resale).

### 5. Licence
The file must declare the licence under which the content is published (for example: license: MIT, CC-BY-4.0, or custom). The licence name must correspond to a publicly documented licence or a clearly described custom licence.

### 6. Rights Update Policy
The file must declare how rights information is updated when content changes (for example: rights-update: on-change or rights-update: versioned).

### 7. Proof of Integrity
The file must include a line using the sha256: key containing the SHA-256 hash of the rights.txt file itself, computed over the exact content of the file excluding the sha256: line. Example: sha256: <sha256_value>

## Example rights.txt file

rights-model: open  
allowed: reuse, share, remix  
forbidden: none  
license: MIT  
rights-update: on-change  
sha256: (SHA-256 of this file, computed without this line)

## How to Verify

Anyone can verify a rights.txt file using any SHA-256 tool:

1. Download the rights.txt file from the root of the domain.  
2. Make a copy of the file and remove the sha256: line from the copy.  
3. Compute the SHA-256 hash of the copy (without the sha256: line) using any local or online tool.  
4. Compare the computed hash with the value published in the sha256: line of the original rights.txt file. They must match exactly.  
5. Independently check each declaration (rights-model, allowed, forbidden, licence, rights-update) against the actual usage of the content and any visible licence notices.  
6. If any declaration cannot be verified or is contradicted by real usage, the implementation of rights.txt on that domain should be treated as non-compliant.

## SHA-256 Verification Tools

Local tools: sha256sum, shasum -a 256, Get-FileHash  
Online tools: https://emn178.github.io/online-tools/sha256_checksum.html, https://hash.expert, https://www.virustotal.com/gui/file-analysis  
Automated verification (optional): https://api.timeproofs.io/api/verify?hash=<SHA256>

## License

This protocol is released under the MIT License.
