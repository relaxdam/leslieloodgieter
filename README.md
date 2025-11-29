# Leslie Loodgieter - Static starter site

This repository contains a starter static website for Leslie Loodgieter (Rotterdam).
It includes English, Dutch, Russian and Ukrainian translations (inline simple i18n),
a Google Forms placeholder for contact, a generated SVG logo and placeholder images from Unsplash.

Files to edit before go-live
- Replace the Google Forms iframe src (index.html) with your form embed link.
- Optionally add a privacy.html file and cookie notice (required by law in many cases).
- Add your own project photos to images/ and replace Unsplash links if you prefer local images.
- Add postal code / full street address in the JSON-LD if you want.

How to push & enable GitHub Pages (quick)
1. Locally:
   - git init
   - git add .
   - git commit -m "Initial site for Leslie Loodgieter"
   - git branch -M main
   - git remote add origin git@github.com:relaxdam/leslieloodgieter.git
   - git push -u origin main
   (Or use the https remote URL)

2. In the GitHub repo settings:
   - Settings → Pages → Source → select Branch: main and folder: / (root) → Save
   - Add the CNAME file (already included) so GitHub Pages will serve at leslieloodgieter.nl.
   - Configure DNS at your registrar: add the GitHub Pages A records (185.199.108.153 etc.) for the root domain and a CNAME for www pointing to relaxdam.github.io.
   - Wait for DNS propagation and enable HTTPS in the Pages settings.

Google Forms integration
- Create a Google Form at https://forms.google.com
- Click Send → Embed (<>) and copy the iframe src
- Replace the iframe src in index.html (search for YOUR_FORM_ID)
Note: file upload fields in Google Forms require respondents to sign in with a Google account.

Email for info@leslieloodgieter.nl — quick options
Option A — Free forwarding (recommended quick):
- Use a forwarding service (ImprovMX or ForwardEmail). They forward all incoming mail to your existing email (Gmail/Outlook).
- Example (ImprovMX):
  1. Register at improvmx.com and add domain leslieloodgieter.nl
  2. Add MX records at your domain registrar:
     - MX mx1.improvmx.com priority 10
     - MX mx2.improvmx.com priority 20
  3. In ImprovMX dashboard: set forward rule info@leslieloodgieter.nl → your real email (e.g., your Gmail).
- To send as info@ from Gmail, configure "Send mail as" with SMTP credentials from an SMTP provider (SendGrid, Mailgun, etc.) or use a paid plan of the forwarding service if available.

Option B — Google Workspace (paid):
- Pros: full mailbox in Gmail UI, reliable sending, DKIM/SPF setup guided.
- Steps: sign up, verify domain (add TXT), set Google MX records, create user info@.

Option C — Registrar mailbox:
- Many registrars provide a mailbox product you can buy. They give MX and SMTP details.

SPF / DKIM:
- If you intend to send mail from info@, set SPF to include your sending provider and configure DKIM per their instructions so emails don't go to spam.

DNS records summary for GitHub Pages
- A 185.199.108.153
- A 185.199.109.153
- A 185.199.110.153
- A 185.199.111.153
- CNAME for www → relaxdam.github.io

Notes about languages
- This starter provides manual translations for English, Dutch, Russian and Ukrainian via a small JS dictionary. It also includes the Google Translate widget as a fallback so visitors can translate into other languages. For SEO and quality, consider professionally translating the main pages you want indexed (nl + en recommended).

If you want me to push the files to GitHub and enable Pages
- I can push the files directly to relaxdam/leslieloodgieter/main and finish setup, but I need you to re-authorize the push (accept the GitHub authorization if it appears). After you confirm authorization I will:
  - commit the updated files,
  - create the main branch if needed,
  - set the repo (public as you requested) and confirm.
- If you prefer to push yourself, use the commands above.