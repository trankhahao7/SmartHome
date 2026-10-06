# Security Policy

## Supported Versions

SmartHome has no published GitHub releases and no formal release-version support policy. Until a release policy is established, security reports are accepted for code on the `main` branch. This statement does not imply that a particular release or deployment is maintained.

## Reporting a Vulnerability

Do not report security vulnerabilities through public GitHub Issues, pull requests, or Discussions. Use [GitHub Private Vulnerability Reporting](https://github.com/trankhahao7/SmartHome/security/advisories/new) to send a private report to the maintainers.

Please include, when known:

- The affected component and commit or version.
- The impact and conditions required to exploit the issue.
- Clear reproduction steps and a proof of concept that does not access or expose other people's data.
- Relevant environment details and sanitized logs.
- A suggested severity or CVSS score and a proposed mitigation, if available.

Do not include passwords, tokens, Wi-Fi credentials, private keys, personal data, or information belonging to other users. Do not publicly disclose the issue while it is being reviewed.

## Response and Coordinated Disclosure

The maintainers aim to:

- Acknowledge a report within 72 hours.
- Provide an initial assessment within 7 days.
- Send progress updates every 7 to 14 days while the report is being investigated.
- Coordinate public disclosure with the reporter, with a target of disclosure within 90 days of the initial report.

These are targets and may be affected by severity, reproducibility, maintainer availability, and remediation complexity. The 90-day target is not a promise that a fix will be available by that date. If a coordinated disclosure date cannot be met, the maintainers will discuss an extension with the reporter where possible.

The intended process is to acknowledge the report, assess and reproduce it, determine impact and affected code, prepare and verify a fix where feasible, and coordinate a public advisory. A CVE may be requested when appropriate and available. No bug bounty or guaranteed response service is offered.

## Scope

Reports may cover vulnerabilities in SmartHome source code and official project components. The repository has no published releases, so the current report scope is code on `main`.

For a vulnerability in a third-party dependency, report it to that dependency's maintainers and notify SmartHome privately if the project's use is affected. Automated scanner output without a reproducible security impact, vulnerabilities in a user's local configuration, social engineering, and disruptive denial-of-service testing are not a substitute for a focused vulnerability report. Do not test against systems or devices that you do not own or have explicit permission to assess.

## Safe Harbor

For security research that is conducted in good faith, complies with applicable law, follows this policy, avoids accessing or disclosing private data, and does not disrupt services or devices, SmartHome maintainers will not initiate legal action solely for activities within that scope. Stop testing and report promptly if you encounter data that is not yours or an unintended impact. This statement does not authorize unlawful activity or testing of third-party systems, and it does not bind parties outside the project maintainers' control.

## Credit

With the reporter's consent, the maintainers may acknowledge them in a security advisory or release note. A reporter may request to remain anonymous; no identifying information will be published without permission.

## User Recommendations

Keep local checkouts updated from the project's `main` branch and review repository security advisories. There are no published release artifacts or checksums to verify at this time. Do not expose the current prototype directly to the public Internet; see the security limitations in the [README](README.md#limitations-and-security).
