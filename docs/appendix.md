[Back to README](../README.md)

# Appendix

## Glossary

| Term | Meaning |
| --- | --- |
| n8n | Workflow automation tool used as the orchestration layer |
| RPA | Robotic Process Automation, used here for attended browser/mobile publishing |
| Appium | Mobile automation framework for Android/iOS apps |
| WebdriverIO | Automation client used with Appium |
| Playwright | Browser automation framework |
| Adapter | Publishing lane implementation such as direct API or attended RPA |
| Human intervention | State where the operator must resolve login, CAPTCHA, 2FA, warning, or UI issue |

## Safety Checklist

Do not include:

- `.env` files or tokens.
- n8n credentials.
- Browser profiles, cookies, or session files.
- Downloaded real media.
- Real account names, phone numbers, emails, or platform identifiers.
- Raw workflow exports containing private credential references.

## Reviewer Checklist

| Reviewer | What To Look For |
| --- | --- |
| Hiring manager | Product thinking, safety awareness, and end-to-end ownership |
| Automation engineer | Workflow routing, RPA boundaries, and recovery states |
| AI automation reviewer | Orchestration quality and human-in-the-loop design |
| Graduate supervisor | Problem framing, system architecture, and trade-off reasoning |

