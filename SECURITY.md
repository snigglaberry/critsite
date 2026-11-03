# Security Policy

Crit Launcher is open source, and we take the security of the launcher and its users seriously. Thank you for helping keep it safe.

## Reporting a vulnerability

**Please do not open a public issue for security problems.** Report them privately instead:

1. Go to the [Security tab](https://github.com/snigglaberry/crit-launcher/security) of this repository.
2. Click **Report a vulnerability** (or use [this direct link](https://github.com/snigglaberry/crit-launcher/security/advisories/new)).
3. Describe the problem, the version you tested, your operating system, and the steps to reproduce it.

Helpful things to include: a proof of concept, the impact you think it has, and any suggested fix.

We aim to acknowledge reports within 7 days and to keep you updated until the issue is resolved. Please give us reasonable time to ship a fix before you disclose the problem publicly. We are happy to credit you in the release notes if you would like.

## Supported versions

Security fixes are released for the **latest version** of Crit Launcher. Please update to the newest release before reporting, in case the problem is already fixed.

## What is in scope

- The Crit Launcher application and the Crit Client integration
- The Horizon Loader (Rust) and its file handling, integrity checks and game startup
- Account and token handling, and anything that could expose credentials
- Download and update logic, including Java runtime and mod downloads
- The official website, [critlauncher.xyz](https://critlauncher.xyz)

## What is out of scope

- Vulnerabilities in Minecraft, Mojang or Microsoft services, Modrinth, CurseForge, or third-party mods. Please report those to their own maintainers.
- Problems that need an attacker to already have full control of your computer.
- Social engineering, spam, or denial-of-service attacks against our infrastructure.
- Unofficial builds, forks, or apps that use the Crit Launcher name (see below).

## Antivirus warnings

Crit Launcher is new and is **not yet code-signed**, so some antivirus programs show false-positive warnings. These are not vulnerabilities, and you do not need to report them as security issues. If you want, you can open a normal issue with the scanner name and version so we can submit a false-positive report. We plan to buy a code-signing certificate.

## Verifying your download

Only download Crit Launcher from this repository or from [critlauncher.xyz](https://critlauncher.xyz). To check that your file is genuine, compare its SHA-256 hash with the checksum published with the release.

**Windows (PowerShell)**

```powershell
Get-FileHash .\CritLauncher.exe -Algorithm SHA256
```

**Linux**

```bash
sha256sum crit-launcher-bin
```

You can also build the launcher yourself from the public source code.

## Privacy

Crit Launcher does not collect telemetry or analytics. See the [FAQ](https://critlauncher.xyz/faq) for details.
