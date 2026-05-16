# Security Policy

## Supported Versions

| Version | Supported |
|---------|-----------|
| Latest  | ✅ Yes    |
| Older   | ❌ No     |

Only the latest version of BedrockAddonStudio receives security fixes.

## Reporting a Vulnerability

If you discover a security vulnerability, **please do not open a public issue.**

Instead, report it privately by emailing or opening a [GitHub Security Advisory](https://github.com/alamien060512-alt/BedrockAddonStudio/security/advisories/new).

Please include:
- A description of the vulnerability
- Steps to reproduce it
- Potential impact
- Any suggested fix if you have one

You can expect a response within **72 hours**. If the vulnerability is confirmed, a fix will be prioritized and credited to you in the release notes (unless you prefer to stay anonymous).

## Scope

This is a **client-side only** tool — it runs entirely in the browser with no server, no database, and no user accounts. No data is transmitted anywhere.

Security concerns most relevant to this project:

- Malicious input in JSON fields being executed (XSS)
- Zip file generation producing unexpected file paths (zip slip)
- Injected content in exported `.mcaddon` files that could affect Minecraft

## Out of Scope

- Issues with third-party libraries (JSZip, etc.) — report those upstream
- Browser-specific bugs unrelated to security
- Issues in forks or modified versions of this project
