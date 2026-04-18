# Kyle's Onboarding Guide - Mika Jaymes Theme Development

Welcome to the Mika Jaymes Shopify theme project. This guide gets you from zero to coding in 10 minutes.

---

## Prerequisites

You'll need these installed on your machine:

- **Node.js** (v18+) - [Download](https://nodejs.org/)
- **Git** - [Download](https://git-scm.com/)
- **A code editor** (VS Code recommended)

---

## Step 1: Install Shopify CLI

```bash
npm install -g @shopify/cli @shopify/theme
```

Verify it's installed:

```bash
shopify version
```

You should see something like `3.x.x`.

---

## Step 2: Clone the Repo

```bash
git clone https://github.com/thecometcompanies/mikajaymes.git
cd mikajaymes
```

---

## Step 3: Authenticate with Shopify

```bash
shopify auth login --store mikajaymes.myshopify.com
```

This will open your browser. Log in with the **staff account credentials** Michael gave you.

Your staff account only has access to theme development - you cannot affect the live store.

---

## Step 4: Pull the Development Theme

```bash
shopify theme pull --development
```

This downloads a copy of the theme files to your local machine as a **development theme**. It does NOT touch the live theme.

---

## Step 5: Start the Dev Server

```bash
shopify theme dev --store mikajaymes.myshopify.com
```

This will:
1. Create (or reuse) your personal **development theme** on Shopify
2. Start a local server (usually `http://127.0.0.1:9292`)
3. Open a preview in your browser
4. **Hot-reload** every time you save a file

The development theme is:
- Completely isolated from the live theme
- Only visible to you (not customers)
- Automatically created per developer

---

## Step 6: Make Changes

Edit files in your local `mikajaymes/` directory. Changes appear instantly in your browser preview.

### Key files you'll work with:

| File/Folder | What's in it |
|-------------|-------------|
| `layout/theme.liquid` | Main HTML wrapper (head, body, scripts) |
| `sections/` | Reusable content blocks (hero, featured products, etc.) |
| `snippets/` | Small reusable pieces (buttons, cards, icons) |
| `templates/` | Page layouts (homepage, product page, collection, etc.) |
| `assets/` | CSS, JavaScript, images, fonts |
| `config/settings_schema.json` | Theme customizer settings |

---

## Step 7: Save Your Work to GitHub

When you've made changes you're happy with:

```bash
# See what changed
git status

# Stage your changes
git add .

# Commit with a descriptive message
git commit -m "feat: add new hero section to homepage"

# Push to GitHub
git push origin main
```

### Commit message prefixes:

| Prefix | When to use |
|--------|------------|
| `feat:` | New feature or section |
| `fix:` | Bug fix |
| `style:` | Visual/CSS changes |
| `refactor:` | Code cleanup (no visual change) |
| `chore:` | Config, dependencies, tooling |

---

## Step 8: Submit for Review

When you want Michael to review your work:

```bash
# Push to Shopify as an unpublished theme
shopify theme push --unpublished
```

Then message Michael in Slack with:
- What you changed
- The preview link (Shopify will give you one)

Michael will review and publish when ready.

---

## Rules

### DO
- Use `shopify theme dev` for all development
- Use `--development` flag when pushing to Shopify
- Commit and push to GitHub frequently
- Ask in Slack if you're unsure about anything
- Create feature branches for big changes: `git checkout -b feature/new-header`

### DO NOT
- Never run `shopify theme push --live`
- Never run `shopify theme publish`
- Never run `shopify theme delete`
- Never run `shopify theme push` without a flag (it may default to live)
- Never edit the live theme directly in Shopify Admin

---

## Troubleshooting

### "You don't have permission"
Your staff account may not have the right permissions. Message Michael in Slack.

### "Theme not found"
Run `shopify theme list` to see available themes. Use `shopify theme dev` to create a new dev theme.

### "Port already in use"
Another process is using port 9292. Either kill it or use a different port:
```bash
shopify theme dev --port 9293
```

### Hot reload stopped working
Stop the server (Ctrl+C) and restart:
```bash
shopify theme dev --store mikajaymes.myshopify.com
```

### Need to start fresh
```bash
# Pull a clean copy of the theme
shopify theme pull --development
```

---

## Resources

- [Shopify Theme Docs](https://shopify.dev/docs/themes)
- [Liquid Reference](https://shopify.dev/docs/api/liquid)
- [Dawn Theme (our base)](https://github.com/Shopify/dawn)
- [Shopify CLI Docs](https://shopify.dev/docs/api/shopify-cli)

---

## Contact

Questions? Message Michael in Slack. Don't guess - ask.
