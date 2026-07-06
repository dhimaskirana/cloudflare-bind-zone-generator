# Cloudflare BIND Zone Generator (Ultimate Edition)

A simple, lightning-fast, and secure client-side web utility built with **Astro** to generate BIND zone configuration files formatted specifically for seamless **Cloudflare DNS Import**. 

Instead of adding records one by one through the Cloudflare GUI, this tool lets you fill out a smart form, preview the output in real-time, and import all your DNS records in bulk within seconds.

## Key Features

- **100% Client-Side:** No databases, no tracking. Your IP address, domains, and keys never leave your browser.
- **Interactive Live Preview:** Watch your BIND zone file update in real-time as you type.
- **Smart Validation & Cleaning:** Automatically strips out `https://`, `www.`, and trailing slashes from domain inputs to prevent syntax errors.
- **Cloudflare Proxy Aware:** Appends `;cf_proxy=true` or `;cf_proxy=false` intelligently so Cloudflare applies the "Orange/Grey Cloud" toggle perfectly upon import.
- **Dual-Stack Ready:** Supports both **IPv4 (A records)** and optional **IPv6 (AAAA records)**.
- **Advanced Mail Suite Templates:** Quick configuration dropdown for:
  - **Local/Self-hosted Server** (Standard MX & local SPF)
  - **Google Workspace** (Updated 5 MX records + Google SPF)
  - **Microsoft 365** (Outlook protection MX + autodiscover CNAME + M365 SPF)
  - **Mailgun** (Transactional email records setup)
- **Email Security Wizard:** Easily generate standard **DKIM** text records and **DMARC anti-spoofing policies** to keep your emails out of the spam folder.
- **Fully Responsive Design:** Mobile-first layout optimized to prevent field overflow on smaller screens.

---

## Tech Stack

- [Astro](https://astro.build/) - Modern component-based web framework.
- Vanilla JavaScript & TypeScript Types (Zero external NPM dependencies for the core tool).
- Standard Web API Blobs (for client-side file compiling and triggers).

---

## Local Development

Follow these steps to run the project locally on your machine:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/dhimaskirana/cloudflare-bind-zone-generator.git
   cd YOUR_REPO_NAME
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   ```
   Open `http://localhost:4321` in your browser to see the app running.

4. **Build for production:**
   ```bash
   npm run build
   ```

---

## How to Use it in Cloudflare

1. Open the tool, input your **Domain** (e.g., `mywebsite.com`) and your **Server IPv4/IPv6**.
2. Choose your **Mail Provider** and configure **DKIM/DMARC** if needed.
3. Review the generated configuration on the **Live Zone File Preview** panel.
4. Click **Download BIND Zone File (.txt)**.
5. Log in to your **Cloudflare Dashboard** and select your website zone.
6. Navigate to **DNS** -> **Records**.
7. On the right side next to the "Add record" button, click the **Advanced** dropdown and select **Import**.
8. Upload the downloaded `.txt` file. All your complex records, proxies, and priorities will be populated instantly!

---

## Security & Privacy

This application is engineered strictly as a static utility. It utilizes the browser's native `Blob` and `URL.createObjectURL` interfaces to handle all string manipulation and file downloads completely in memory. **No analytical or telemetry data is collected.**

---

## License

Distributed under the MIT License. See `LICENSE` for more information.