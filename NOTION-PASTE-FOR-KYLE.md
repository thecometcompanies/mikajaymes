---

## Kyle - Shopify Theme Dev Setup

### GitHub Repo
https://github.com/thecometcompanies/mikajaymes

### Step 1: Get Access (one-time setup)

1. Go to [partners.shopify.com](https://partners.shopify.com) and create a **free** Partner account
2. In the Partner dashboard: **Stores → Add store → Managed stores**
3. Enter `mikajaymes.myshopify.com` and submit a collaborator request
4. Wait for Michael to approve (you'll get an email)
5. You'll have **Themes-only** access — you can't touch the live store

### Step 2: Set Up Your Machine

```bash
# Install Shopify CLI
npm install -g @shopify/cli @shopify/theme

# Clone the repo
git clone https://github.com/thecometcompanies/mikajaymes.git
cd mikajaymes

# Log in with your Partner account credentials
shopify auth login --store mikajaymes.myshopify.com

# Pull the dev theme files
shopify theme pull --development
```

### Step 3: Start Coding

```bash
# Start the dev server (opens a local preview that hot-reloads)
shopify theme dev --store mikajaymes.myshopify.com
```

Edit files locally. Changes appear instantly in your browser.

### Step 4: Save & Submit

```bash
# Save to GitHub
git add .
git commit -m "feat: what you changed"
git push origin main

# When ready for Michael to review
shopify theme push --unpublished
# Send Michael the preview link in Slack
```

### Safety Rules

**SAFE commands (use these):**
- `shopify theme dev` — local development
- `shopify theme push --development` — push to your dev theme
- `shopify theme push --unpublished` — create review copy

**NEVER use these commands:**
- `shopify theme push --live` (overwrites live site)
- `shopify theme publish` (makes a theme live)
- `shopify theme delete` (permanently deletes)
- `shopify theme push` without a flag

### Full Setup Guide
See [KYLE-SETUP.md](https://github.com/thecometcompanies/mikajaymes/blob/main/KYLE-SETUP.md) in the repo for detailed instructions, troubleshooting, and project structure.

### Resources
- [Shopify Theme Docs](https://shopify.dev/docs/themes)
- [Liquid Template Language](https://shopify.dev/docs/api/liquid)
- [Dawn Base Theme](https://github.com/Shopify/dawn)
