# BL Blossom & Co. — Website Setup Guide (Login Dashboard Edition)

Your site now has a real, password-protected admin page where you can log in and edit content, upload photos, and turn things on/off — no code, no spreadsheets. This replaces the old Google Sheet control panel; you can ignore that earlier CSV file and guide.

This setup is a bit more involved than the drag-and-drop version because a login dashboard needs somewhere to save your changes. That "somewhere" is a free GitHub account, which quietly stores your website's files and lets the dashboard update them when you hit Save. You'll only do this setup once — after that, updating your site is just logging in and editing.

**What's in the folder I sent you:**
- `index.html` — your website
- `content.json` — the file your dashboard edits (banners, descriptions, links, etc.)
- `admin/` — your login dashboard
- `images/uploads/` — where photos you upload will live

---

## Step 1 — Create a free GitHub account

1. Go to [github.com](https://github.com) and sign up (free plan is all you need).
2. Once signed in, click the **+** in the top right → **New repository**.
3. Name it something like `bl-blossom-website`. Keep it **Private** or **Public** — either works. Click **Create repository**.

## Step 2 — Upload your website files to GitHub

1. On your new repository's page, click **uploading an existing file** (or **Add file → Upload files**).
2. Drag in everything from the folder I sent you: `index.html`, `content.json`, the whole `admin` folder, and the whole `images` folder.
3. Scroll down and click **Commit changes**.

## Step 3 — Connect Netlify to that GitHub repo

If your site is already live on Netlify from the drag-and-drop method, you'll now switch it to deploy from GitHub instead — this is what makes the login dashboard able to save changes.

1. Log into [netlify.com](https://netlify.com).
2. Click **Add new site → Import an existing project**.
3. Choose **GitHub**, authorize Netlify to access your account, and select the `bl-blossom-website` repository.
4. Leave the build settings blank (no build command, publish directory is the root `/`) and click **Deploy**.
5. Netlify will give this new site a random name like `curious-swan-123.netlify.app`. Confirm it loads your site correctly.
6. **Move your custom domain over:** in your *old* drag-and-drop Netlify site, go to **Domain settings** and remove `blblossomco.com` from that site. Then in this *new* Git-connected site, go to **Domain settings → Add a domain**, and add `blblossomco.com`. Your DNS records from before stay the same — you're just pointing the domain at the new site.
7. Once that's done, you can delete the old drag-and-drop site in Netlify (optional, but keeps things tidy).

## Step 4 — Turn on Netlify Identity (this is your login system)

1. On your new site in Netlify, go to the **Identity** tab and click **Enable Identity**.
2. Under **Registration preferences**, set it to **Invite only** (so random people can't create accounts on your site).
3. Under **Identity → Services**, find **Git Gateway** and click **Enable Git Gateway**. This is what lets your login connect to your GitHub files.

## Step 5 — Invite yourself as the site owner

1. Still under the **Identity** tab, click **Invite users**, and enter your own email (`blblossomco@gmail.com`).
2. Check your email for the invite, click the link — it'll take you to your site and ask you to set a password.
3. Once you set a password, you're logged in and registered as an admin user.

## Step 6 — Log in and start editing

1. Go to `blblossomco.com/admin` (or your Netlify subdomain + `/admin` if the custom domain isn't pointed yet).
2. Log in with the email and password from Step 5.
3. You'll see a form-based dashboard with sections for:
   - The announcement banner (turn on/off, edit the text — great for sales and holidays)
   - Whether prices show publicly (leave this off unless you decide to display pricing again)
   - Whether the reviews section shows (turn on once you've added real reviews below)
   - Your Instagram/TikTok links and contact email
   - Each collection's description, availability toggle, and photo upload
   - Up to 5 customer reviews (quote + who it's from)
4. Make your changes and click **Save** (top right) — this updates your live website automatically, usually within a minute.

**Uploading real product photos:** in any of the "Photo" fields, click to upload — drag in a picture from your phone or computer, and it replaces the placeholder graphic on that collection card. See the separate note I sent about getting good photos of your baskets before uploading.

---

## Website analytics (Google Analytics 4)

This part is unchanged from before and doesn't depend on GitHub — it's already wired into your site's code.

1. Go to [analytics.google.com](https://analytics.google.com) and create a free account if you don't have one.
2. Create a new **Property** for "BL Blossom & Co." and a **Web** data stream using `blblossomco.com`.
3. Copy the **Measurement ID** (looks like `G-XXXXXXXXXX`).
4. Send it to me and I'll drop it into your site, or open `index.html` yourself, search for `G-XXXXXXXXXX` (appears twice near the top), and replace both with your real ID. Then re-upload that file to GitHub the same way as Step 2.

**Where to see your data** (Google Analytics → Reports):
- **Acquisition** — where visitors came from (Instagram, TikTok, direct, search)
- **Engagement → Pages and screens** — most-visited pages
- **Tech → Tech details** — device type
- **User → Demographics details** — city-level location (needs some traffic first)
- **Engagement → Events** — look for `cta_click`, `request_quote_click`, `social_click`, `email_click`, `custom_order_submitted`, and `contact_form_submitted` — these track the specific buttons and forms you asked about.

Data usually starts appearing within 24–48 hours of your first real visitor.

---

## If any of this feels like a lot

The setup above (Steps 1–5) is genuinely the fiddly, one-time part — mostly clicking "Enable" and "Invite" a few times across two websites (GitHub and Netlify). Once it's done, Step 6 (logging in and editing) is the only thing you'll ever need to do day-to-day. If you get stuck on any step, tell me exactly where and what you're seeing, and I can walk you through it or troubleshoot from there.
