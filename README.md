# Mika Jaymes - Shopify Theme Development

> Official theme development repo for [mikajaymes.com](https://mikajaymes.com)

---

## Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/thecometcompanies/mikajaymes.git
cd mikajaymes

# 2. Install Shopify CLI (if not already installed)
npm install -g @shopify/cli @shopify/theme

# 3. Set up Collaborator access (see KYLE-SETUP.md for details)
#    - Create free Partner account at partners.shopify.com
#    - Request collaborator access to mikajaymes.myshopify.com
#    - Wait for Michael to approve

# 4. Authenticate with the store
shopify auth login --store mika-jaymes.myshopify.com

# 5. Pull the current dev theme to work on
shopify theme pull --development

# 6. Start local dev server (creates a safe, unpublished dev theme)
shopify theme dev --store mika-jaymes.myshopify.com
```

Your browser will open a local preview. All changes hot-reload instantly.

---

## Safe Commands (USE THESE)

| Command | What It Does |
|---------|-------------|
| `shopify theme dev` | Starts local dev server with a temporary dev theme |
| `shopify theme pull --development` | Pulls the dev theme files to your local machine |
| `shopify theme push --development` | Pushes your local changes to the dev theme |
| `shopify theme push --unpublished` | Creates a new unpublished theme for review |
| `shopify theme list` | Lists all themes and their IDs |
| `shopify theme info` | Shows info about the current theme |

## DANGEROUS Commands (NEVER USE)

| Command | Why It's Dangerous |
|---------|-------------------|
| `shopify theme push --live` | Overwrites the LIVE customer-facing theme |
| `shopify theme publish` | Makes any theme the active live theme |
| `shopify theme delete` | Permanently deletes a theme |
| `shopify theme push` (no flag) | May prompt to push to live - always specify `--development` |

---

## Development Workflow

```
1. Pull latest from GitHub
   git pull origin main

2. Start dev server
   shopify theme dev --store mikajaymes.myshopify.com

3. Make changes (hot-reloads automatically)

4. When ready, commit and push to GitHub
   git add .
   git commit -m "feat: description of changes"
   git push origin main

5. When ready for Michael to review, push to Shopify as unpublished
   shopify theme push --unpublished
   # Share the preview link in Slack
```

---

## Project Structure (Shopify Dawn-based)

```
mikajaymes/
├── assets/           # CSS, JS, images, fonts
├── config/           # theme settings (settings_schema.json, settings_data.json)
├── layout/           # theme.liquid (main wrapper)
├── locales/          # translation files
├── sections/         # reusable page sections
├── snippets/         # partial templates (reusable chunks)
├── templates/        # page templates (JSON or Liquid)
│   └── customers/    # account page templates
└── README.md
```

---

## Git Workflow

- **Branch**: `main` is the source of truth
- **Feature branches**: Create `feature/your-feature-name` for big changes
- **Commits**: Use conventional commits (`feat:`, `fix:`, `style:`, `refactor:`)
- **PRs**: Open a pull request for review before merging to main

---

## Team

| Role | Person | Contact |
|------|--------|---------|
| Owner / Creative Director | Michael Monfared | Slack DM |
| Vibe Coder / Theme Developer | Kyle | Slack DM |

---

## Important Notes

- The **live theme is protected**. Only Michael can publish themes.
- Always use `--development` flag when pushing to Shopify.
- If you're unsure about a command, ask in Slack first.
- Preview your dev theme at the URL shown when you run `shopify theme dev`.
