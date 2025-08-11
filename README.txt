
Home Economics — Landing Page (ready to deploy)
==============================================

What I built for you:
- A responsive landing page (index.html) using Tailwind CSS (via CDN).
- WhatsApp "Book Now" button pre-configured with your number.
- Instagram & Facebook links included.
- Contact form defaults to `mailto:` so messages open the user's email app (simple, no backend).
- Instructions included to wire up form submissions to your Gmail using Formspree or Vercel serverless + nodemailer (see below).

Files included:
- index.html        (main website)
- assets/logo.png   (your logo)
- README.txt        (this file)

How to preview locally:
1) Open index.html in your browser (double-click or use Live Server in VS Code).

Quick steps to get this live on Vercel (free):
1) Create a free Vercel account at https://vercel.com/
2) Install Git locally and create a new repo with these files OR drag-and-drop the project folder into Vercel's "New Project" -> "Import" -> "Upload" area.
3) Deploy — Vercel will give you a live URL like https://home-economics-xyz.vercel.app
4) (Optional) Buy a custom domain from Namecheap/GoDaddy and add it under the Vercel project's Domains settings.

How to receive form submissions directly to your Gmail (two options):

Option A — Formspree (easiest, no server):
1) Sign up at https://formspree.io (free tier exists).
2) Create a new form and copy the endpoint URL (e.g. https://formspree.io/f/abcde).
3) Open index.html and change the <form ... action="mailto:..."> to action="https://formspree.io/f/abcde" and method="POST".
4) In Formspree, set your target email to homeeconomics2025@gmail.com (they'll guide you through verification).
5) Deploy the updated site to Vercel.

Option B — Vercel serverless + Gmail SMTP (more control):
1) Deploy the site to Vercel.
2) Add environment variables in Vercel for SMTP (e.g. SMTP_HOST, SMTP_USER, SMTP_PASS — use Gmail's app password if using Gmail).
3) Add an API route at /api/send.js using nodemailer to accept POSTed form data and send email to homeeconomics2025@gmail.com.
4) Change the form in index.html to submit via fetch() to '/api/send' (POST).
5) This method requires basic Node.js setup but gives you more control and removes third-party form services.

Need help?
Tell me if you'd like me to:
- Deploy this to Vercel for you and connect a domain (I can give step-by-step and prepare the repo).
- Set up Formspree and configure it to send to your Gmail.
- Create the Vercel serverless function (I'll prepare the code, but you'll need to provide an SMTP password or use a transactional email service).
