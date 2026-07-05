# Cloudflare BIND Zone Generator

A simple, fast, and secure client-side web utility to generate BIND zone configuration files formatted specifically for seamless **Cloudflare DNS Import**. 

Instead of adding records one by one through the Cloudflare GUI, this tool lets you fill out a simple form, generate a `.txt` zone file, and import it to Cloudflare in bulk.

## Features

- **100% Client-Side:** No databases, no tracking. Your IP address and domain information never leave your browser.
- **Cloudflare Proxy Aware:** Automatically appends the `;cf_proxy=true` or `;cf_proxy=false` comments so Cloudflare sets up the "Orange/Grey Cloud" toggle perfectly upon import.
- **Fast Core Setup:** Generates root `@`, `www`, `ssh`, and `ftp` records instantly.
- **Optional Mail Suite:** Toggleable standard mail configurations including `MX`, `mail` A record, and basic `SPF` security record.

---

## Local Development

Follow these steps to run the project locally on your machine:

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Start the development server:**
   ```bash
   npm run dev
   ```

3. **Build for production:**
   ```bash
   npm run build
   ```