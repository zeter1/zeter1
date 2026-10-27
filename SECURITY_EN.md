**Язык / Language:** [Русский](SECURITY.md) · **English**

[Profile](README_EN.md) · [Support](SUPPORT_EN.md) · [Contributing](CONTRIBUTING_EN.md)

# Security: reporting a potential vulnerability

This is a general reporting route for projects listed on the `zeter1` profile. A repository-specific `SECURITY.md`, if present, takes precedence. This document does not imply that every project has the same maintenance status or that distributed binaries are code-signed.

## Report privately

If an issue might expose data, trigger unintended code execution, bypass a security boundary, or destroy user files, **do not post exploit steps, credentials, dumps, tokens, or personal information in a public issue**.

Email [zeter11@gmail.com](mailto:zeter11@gmail.com) with subject “Security: project name” and include:

1. Repository, version, release or commit, and affected operating system/browser.
2. The suspected impact and minimal, safe reproduction steps on **your own test data**.
3. Observed versus expected behavior, plus what you have and have not verified.
4. If needed, a redacted log excerpt or screenshot free of secrets.

Do not send live passwords, API keys, customer data, or other people's files. Do not probe systems you do not own or have authorization to test. Agree on a secure transfer method before sending any sensitive artifact.

## Follow-up

The maintainer may ask for more details, evaluate impact, and prepare a fix with a regression test. **There is no guaranteed response time, bug bounty, or SLA.** Please avoid disclosing weaponizable details publicly until disclosure has been coordinated.

For ordinary bugs, feature suggestions, or installation issues, use [support](SUPPORT_EN.md). For contributions, see [contributing](CONTRIBUTING_EN.md).
