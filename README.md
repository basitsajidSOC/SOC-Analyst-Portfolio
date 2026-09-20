# Phishing Simulation & Credential Harvesting Lab (Gophish) Project#1

An authorized, educational cybersecurity portfolio project demonstrating phishing simulation mechanics, credential harvesting workflows, and campaign metric tracking using local infrastructure.

## Architecture & Tools
* **Phishing Framework:** Gophish (running locally)
* **SMTP Delivery Sandbox:** Mailtrap (secure email delivery and template inspection)
* **Target OS:** Ubuntu / Windows 10 Virtual Machines (VirtualBox)
* **Analysis Tools:** Firefox, Gophish Campaign Dashboard

## Workflow & Implementation
1. **User Group & Target Setup:** Configured targeted test recipient profiles.
2. **Sending Profile:** Integrated Mailtrap SMTP server credentials for safe testing without external transmission.
3. **Email Template:** Crafted a professional security alert template embedding unique Gophish tracking links (`{{.URL}}`).
4. **Landing Page:** Cloned an authentication portal to evaluate user interaction and form submission mechanics.
5. **Campaign Execution & Monitoring:** Tracked campaign telemetry through the Gophish dashboard across all lifecycle phases:
   - *Email Sent*
   - *Email Opened*
   - *Clicked Link*
   - *Submitted Data (Credential Capture)

