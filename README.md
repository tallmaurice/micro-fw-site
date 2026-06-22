# micro-fw.com

One-page site for Mike Roselli's financial-wellness business.

## How it's hosted
Static site on **GitHub Pages**. The `CNAME` file points the custom domain **micro-fw.com** at it. There's no build step — `index.html` is served as-is. Any push to the default branch republishes within ~a minute.

## Updating the site
- **Owner's guide (for Mike):** see [`START-HERE.md`](START-HERE.md) — the full ELI5 walkthrough (account, transfer, DNS, editing text + images, undo). This is the doc to hand off.
- **Replacing the design:** drop the exported files from Claude Design in here (replace `index.html` and add any assets), keep `CNAME` as-is, commit, push.

## First-time deploy (one-time)
1. Create the repo under the **owner's GitHub account** (the goal is Mike's account — see the AIOS brief for the ownership/transfer plan). Push these files.
2. Repo **Settings → Pages** → Source: deploy from the default branch, root. Then set the custom domain to `micro-fw.com` in that same Pages panel — GitHub creates the `CNAME` file automatically. (The repo ships WITHOUT a CNAME so the `*.github.io` URL works immediately; CNAME appears once the domain is connected.)
3. Configure DNS at **Namecheap** (see below).
4. Once the cert provisions, enable **Enforce HTTPS** in Settings → Pages.

## DNS at Namecheap (micro-fw.com)
Namecheap → **Domain List** → **Manage** (micro-fw.com) → **Advanced DNS**:
1. **Delete** Namecheap's default records that would conflict — the parking-page `CNAME` on host `@` and any `URL Redirect Record`.
2. Add four **A Record**s, all on host `@`, pointing the apex at GitHub Pages:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
3. Add one **CNAME Record**: host `www` → value `<github-username>.github.io.` (trailing dot).
4. Leave TTL on Automatic. Propagation is usually minutes, occasionally up to a few hours.

(GitHub's apex IPs above are current as of 2026-06; if Pages ever fails to verify the domain, re-check them against GitHub's "Managing a custom domain" docs.)
