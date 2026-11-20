---
name: check-website
description: Use when the user wants to check the security hygiene of a website they operate (HTTPS, security headers, DNS, SPF/DKIM/DMARC, exposed files, cookie and privacy-related technical points) or asks how to fix such a finding.
---

# Check a website with Domainwächter

1. Ask which domain the user operates. The check covers only sites the user is allowed to check; the server asks for a verification file before the first analysis.
2. Call `analyze_website` with the domain. If it returns verification steps, show them to the user and wait until the file is uploaded, then call it again.
3. The check takes about two minutes. Then call `get_analysis` with the `job_id`.
4. Report the score and the findings by severity in plain words. Say which are urgent and which can wait.
5. Offer the repair guide from the result. Make changes to the website only with the user's explicit consent and with access the user granted on purpose; explain each change first.
6. This is a technical check, not legal or professional advice.
