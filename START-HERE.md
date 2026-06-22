# Micro Financial Wellness — Your Website Owner's Guide

Hey Mike — this walks you through everything: getting your web address working, editing the site, swapping photos, and never being stuck. No tech background needed. Take it one step at a time, and don't rush. Anytime a word looks scary, there's a plain-English meaning right next to it. You genuinely cannot break this permanently — every change can be undone.

## The 30-second picture
Your website is a few simple files (mostly one file that holds all your words). Those files live on a free service called **GitHub** — think of it as a filing cabinet in the cloud that also publishes your site to the internet. Your web address, **micro-fw.com**, is rented from **Namecheap**. The one-time job is connecting those two so that typing micro-fw.com shows your site. After that, running it is just editing words and pictures in your browser.

You do the setup (Part 1) **once**. Everything after that is just edits.

A few words you'll see:
- **GitHub** — the free site that stores your files and publishes your site online.
- **Repository (or "repo")** — just a folder of your site's files on GitHub.
- **GitHub Pages** — the free feature that turns that folder into a live website.
- **DNS** — the internet's phone book; it connects your web address to your site.
- **A record / CNAME** — specific phone-book entries you'll add (just copy-paste).

---

## Part 1 — One-time setup

### Step 1 — Maurice gets it live and hands it to you
Maurice publishes the first version, then **transfers** the site to your own GitHub account so it's 100% yours. You'll get an email from GitHub asking you to accept it. Before that happens, do Step 2 so you have an account ready.

### Step 2 — Make your free GitHub account (~5 min)
1. Go to **github.com** and click **Sign up**.
2. Enter your email, pick a **username** (keep it simple and clean, like `mikeroselli` or `microfw` — it becomes part of your site's behind-the-scenes address), and set a password.
3. Enter the code GitHub emails you.
4. Tell Maurice your username. That's it — free forever.

### Step 3 — Accept the transfer (you become the owner)
Once Maurice transfers it to your username:
1. You'll get a GitHub email: "…wants to transfer **micro-fw-site** to you."
2. Click the link, sign in, click **Accept transfer**.
3. Done. The site now lives at `github.com/YOUR-USERNAME/micro-fw-site` and you own it. Maurice no longer has access unless you invite him.

### Step 4 — Confirm your site is on (GitHub Pages)
1. On your repo page, click **Settings** (top of the page).
2. In the left menu, click **Pages**.
3. Under "Build and deployment," it should say Source = **Deploy from a branch**, Branch = **main** / **(root)**. If not, set that and click **Save**.
4. You should see a free live link like `YOUR-USERNAME.github.io/micro-fw-site`. Click it — that's your site, already online. **This is the link you can share right away** (your real web address, micro-fw.com, comes next).

### Step 5 — Connect micro-fw.com (your real web address, ~10 min)
Two small parts: first tell GitHub your address, then point Namecheap to it. One time only.

**5a, in GitHub:** go to your repo, then **Settings → Pages**, and under **Custom domain** type `micro-fw.com` and click **Save**. (This quietly adds a small `CNAME` file to your repo. That's normal and good, so don't delete it.) If GitHub asks you to "verify" the domain, just send Maurice what it shows.

**5b, in Namecheap:**
1. Log in to **namecheap.com**.
2. Click **Domain List** → **Manage** next to micro-fw.com.
3. Click the **Advanced DNS** tab.
4. **Delete** any record already there on host `@` that's a "CNAME Record," and any "URL Redirect Record" (that's just Namecheap's parking page — we're replacing it).
5. Click **Add New Record** and add these **four A Records** (Type = `A Record`, Host = `@`, TTL = Automatic) — one per value:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
6. Add **one CNAME Record**: Type = `CNAME Record`, Host = `www`, Value = `YOUR-USERNAME.github.io` (your GitHub username).
7. Click the green checkmark to save each one.
8. Now wait. It usually works within 30 minutes, occasionally a few hours. Totally normal — don't panic if micro-fw.com isn't instant.

### Step 6 — Turn on the padlock (HTTPS)
Once the domain connects (give it an hour), go back to GitHub → repo → **Settings → Pages**, and check **Enforce HTTPS**. If it's greyed out, wait a little longer and check again (GitHub is setting up your security certificate). This gives your site the secure padlock. 🎉 Setup done.

---

## Part 2 — Editing your site (the everyday stuff)

Your whole site is one file: **index.html**. Your words live inside it, and you edit it right in your browser.

### Change text (a price, your bio, the phone number)
1. On your repo, click **index.html**.
2. Click the **pencil icon** (top right) — "Edit this file."
3. Press **Ctrl-F** (or **Cmd-F** on a Mac) and search for the words you want to change.
4. Type your new words over the old ones. One rule: **only change words you can read** — leave anything inside `< >` alone (that's the invisible formatting).
5. Scroll down, click **Commit changes**, then **Commit changes** again. ("Commit" just means "save.")
6. Wait about a minute, refresh micro-fw.com. Done.

### Exactly where the common things are (search for these)
- **Prices:** `$49`, `$129`, `$249`
- **Your phone:** `864-232-2881` (appears twice — change both)
- **Booking button link:** `cal.com` (replace with your real scheduling link)
- **Email shown on the site:** `hello@micro-fw.com` (appears a few times — change all)
- **Your bio:** search `I'm Mike Roselli`

### Swap a photo or the logo
Your images live in the **assets** folder: `emblem.png` (logo) and `mike.jpg` (your headshot).
1. On your repo, click **Add file → Upload files**.
2. Drag in your new image, renamed to the **exact same name** (`mike.jpg` or `emblem.png`).
3. Click **Commit changes**. Because the name matches, the site swaps it automatically.
4. Keep photos reasonably sized (under ~1MB) so the page stays fast.
5. **Logo update coming:** when Shann's cleaned-up (vector) version of the logo is ready, swap `emblem.png` for it the exact same way.

### Made a mistake? Nothing is ever lost.
Every save is its own version. To undo, click **Commits** (the little clock/history icon on the repo) — you can see every change and roll one back. If you're unsure, send Maurice the link and he can revert it in seconds.

### The short "please don't touch" list
- Don't delete **index.html** or the **assets** folder. (Once you've connected your domain in Step 5, don't delete the **CNAME** file either — that's what keeps micro-fw.com working.)
- Don't rename files.
- Don't change anything inside `< >` unless you're sure what it is — just the readable words.

### What's yours to change vs. what to ask Maurice for
- **You've got this yourself:** all the words, prices, links, your phone and email, and swapping the logo or your photo.
- **Ask Maurice for:** new sections, a different layout, or any redesign. The look was built in a design tool, so structural changes get re-exported from there. It's quick for him and keeps the design clean. Don't try to rebuild the layout in the editor, you'll just get tangled.

### Nice-to-haves for later (optional, none needed to launch)
Ask Maurice when you want any of these:
- A "send us a message" contact form on the page.
- Simple visitor stats (how many people stopped by).
- Getting your site to show up in Google searches for your name.

---

## Part 3 — A few things to set up separately (these are NOT the website)
The site links out to other tools you'll want working:

1. **Your booking link.** Every "Book a free consultation" button points to a scheduling page. Set up a free **Calendly** or **cal.com**, then paste that link into the site (search `cal.com` and replace it). Until you do, the buttons won't actually book anything.
2. **Your email (hello@micro-fw.com).** Right now that's just text on the page. To make it a real inbox, in Namecheap → your domain, set up free **Email Forwarding** so hello@micro-fw.com forwards to your everyday email. (Or just change the site to an email you already use.)
3. **Getting paid.** The website doesn't collect money — it's your front door. To charge the monthly fees you'll set up something like **Stripe** payment links, or invoice clients yourself, separately.
4. **Keep the domain renewed.** You've got micro-fw.com for 3 years through Namecheap — turn on **auto-renew** so the site never goes dark down the road.

---

## Part 4 — One heads-up worth flagging (not a website thing)
This coaching business is separate from your Northwestern Mutual advisor role, and charging for financial guidance can carry its own licensing, disclosure, or compliance considerations depending on your state and how it overlaps with your existing registrations. This isn't a website issue and it's not legal advice — just worth a quick check with whoever handles your compliance/licensing before you take on paying clients, so you're covered.

---

## When you get stuck
Text Maurice. Or paste what you're trying to do (and the file) into an AI assistant and it'll walk you through it. Remember: you can't break this permanently — everything is undoable. Take your time, one step at a time.
