# Findbar

**Assisted business visibility audits — reviewed, understandable and private.**

Findbar helps an operator check a business website and public local presence, review concrete proposals and deliver a simple private client report. It is part of KiDraht.

## Status · 1 November 2026

**Assisted online pilot · Beta / readiness 70 · Owner UAT pending.** This is a public presentation of private implementation work, not a self-service production release.

- Private invitation link; the business confirms its details and permission without entering the operator Studio.
- Operator-led analysis, three understandable priorities, evidence on demand and reviewed report release.
- DE / EN / SQ portal and reports, PDF export and an email draft with PDF attachment.
- Separate invitation/report access, expiry and revocation; retained evidence and version history.
- Google OAuth/PKCE adapter implemented and tested with simulated transport. The real Google connection is **not yet configured or verified**.

The saved AI sample is kept distinct from new website checks. No claim of guaranteed rankings, AI recommendations or automatic client-site publishing is made.

## Real interface, fictitious demo business

![Private invitation interface](docs/assets/pilot-invitation-demo-de.png)

Actual product UI using a visual fixture for “Café Linden · Demo”. No customer data, customer consent or measured business results are shown. The implementation was separately tested with isolated operator/client sessions.

<details><summary>Mobile invitation</summary>

![Mobile invitation](docs/assets/pilot-invitation-demo-en.png)

</details>

## Verification and limits

201 unit tests passed; the full DB/worker suite passed 42/42, followed by 11/11 focused integration checks after PDF/email refinements. The operator/client journey ran over public HTTPS, with desktop/tablet/mobile checks and three-language PDF downloads. The consent used for QA was explicitly synthetic; no customer approval was impersonated and no email was sent.

Existing owner records, AI studies/costs, encrypted key and original regression export were verified unchanged. Real Google access, real client usability feedback and final owner acceptance remain open.

[Portfolio case study](https://www.redioncekrezi.de/en/projects/findbar)
