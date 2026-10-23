```markdown
# 🎧 Outbound Sales Co-Pilot (PWA)
> An enterprise-grade, privacy-first Progressive Web Application designed specifically for high-volume B2B/B2C outbound sales representatives. Built for lightning-fast live calling, multi-region prospecting, and seamless CRM data export.

---

## 🌟 System Architecture & File Structure

The application is structured as a modular, high-performance Progressive Web App adhering to modern 2026 web standards. All state and custom edits are persisted locally using secure browser storage (`localStorage`).


```

📂 Outbound-Sales-Co-Pilot/
├── 📄 index.html                  # Main application entry point & layout shell
├── 📄 manifest.webmanifest        # PWA manifest (metadata, shortcuts, theme colors)
├── 📄 sw.js                       # Service Worker (offline caching & asset management)
├── 📄 offline.html                # Custom offline fallback view
├── 📄 robots.txt                  # Search engine index blocker (private utility)
├── 📄 README.md                   # System documentation & deployment guide
├── 📁 css/
│   └── 🎨 styles.css              # Custom 2026 dark-mode design system & animations
├── 📁 js/
│   └── ⚡ app.js                  # Core state management, teleprompter, KPIs, and tour logic
├── 📁 icons/                      # Multi-resolution PWA icons (72px to 512px + maskable)
├── 📁 assets/                     # App imagery and branding assets
├── 📁 screenshots/                # Rich installer preview mockups (wide & narrow)
└── 📁 .well-known/
└── 🔗 assetlinks.json         # Digital Asset Links template for Android TWA wrapping

```

---

## 🚀 Key Features & Modules

1. **⏱️ Persistent Top HUD & Global Call Timer**
   - Live call timer (`00:00`) with `Start`/`Reset` controls.
   - Quick increment buttons (`+1 Dial` / `+1 Connect`) accessible instantly from any tab.
   - **Real-Time Global Timezone Bar:** Automatically flags whether it is legally permissible to call prospects in **US Eastern, Central, Pacific, UK, and Central Europe** (Green = 9am–9pm local; Red = outside calling hours).

2. **📜 Tab 1: Live Call Cockpit & Teleprompter**
   - 3-column widescreen layout: Scripts on the left, Pricing Tiers in the center, and Objection Battlecards on the right.
   - **Teleprompter Mode:** Highlights `[Bracketed Placeholders]` in amber for effortless reading.
   - **Compliance Quick Check:** Built-in verification checklist for US/EU calling regulations (DNC screening, recording consent, and cancellation terms).

3. **🗂️ Tab 2: Sales Pipeline & Follow-Up Manager**
   - Log and track warm leads across custom pipeline stages (*Cold Lead, Interested - Sent Info, Warm Follow-Up, Ready to Close, Closed Won*).
   - Filter by follow-up dates and copy pre-formatted, editable email templates that auto-populate your pricing tiers.

4. **📝 Tab 3: Client Listing Intake & CRM Exporter**
   - Record verified subscriber details during live closing calls.
   - Instant one-click export formatted as **JSON, CSV, or Markdown tables** for effortless pasting into Airtable, ClickUp, Notion, or HubSpot.

5. **📊 Tab 4: KPI Tracker & End-of-Day Report**
   - Automatic conversion rate calculators (*Connect rate, Qualify rate, Close rate*).
   - Symmetric 4x2 metrics grid and revenue tracker.
   - Instant **End-of-Day Report Generator** for team updates and management logging.

6. **❓ Help & Guide + ⚙️ Settings Modal**
   - Interactive step-by-step tour and keyboard shortcut reference (`Space` = Timer, `D` = Dial, `C` = Connect, `1–6` = Scripts).
   - Global auto-fill settings for your rep profile (`[My name]`, `[Company]`, `[Website]`) and full JSON backup/restore capabilities.

---

## ⚙️ Deployment & Installation Guide

### 1. Host on Any Static HTTPS Host
Upload all files in the root folder to an HTTPS-enabled static hosting provider:
* **Netlify**, **Vercel**, **Cloudflare Pages**, or **GitHub Pages**.
* *Note:* Service workers and PWA installation strictly require an HTTPS connection (though `localhost` via `python3 -m http.server` works seamlessly for local testing).

### 2. Installing the App on Your Device
* **Desktop (Chrome / Edge):** Open your hosted URL and click the **Install icon** in the browser address bar.
* **iOS (Safari):** Tap the **Share** button in Safari and select **"Add to Home Screen"**.

### 3. Updating Installed Copies (`v5`)
* The service worker cache is pegged to `copilot-v5`. 
* If you already have an older version installed on your device, close and reopen the app once or twice to trigger the background update sequence.

---

## 🛠️ Configuration & Developer Notes

* **Local Storage Persistence:** All scripts, pricing tiers, pipeline leads, intake entries, and KPI counters live entirely in your browser's `localStorage`. They do not auto-sync across different devices. Use the **Settings** menu to export a `.json` backup if migrating workstations.
* **TWA / Play Store Wrapper:** If you intend to wrap this PWA into an Android app package, populate `.well-known/assetlinks.json` with your verified application package name and SHA-256 signing fingerprint.
* **Search Engine Visibility:** `robots.txt` is pre-configured to block search engine indexing to protect your internal sales data.

```
