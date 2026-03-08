# Installation Guide

## Prerequisites

- **Claude Code CLI** installed and configured
- **Git** for cloning the repository

Optional:
- **DataForSEO account** for keywords/backlinks/SERP/AI visibility skills
- **Google Search Console** for monitoring your own site

## Quick Install

```bash
git clone https://github.com/norahe0304-art/30x-seo.git
cd 30x-seo
```

That's it. Claude Code auto-discovers skills from the `skills/` directory.

## Verify Installation

1. Start Claude Code in the repo directory:

```bash
claude
```

2. Check that skills are loaded:

```
/seo
```

You should see the orchestrator prompt.

## DataForSEO Setup (Optional)

Required for: `30x-seo-keywords`, `30x-seo-backlinks`, `30x-seo-serp`, `30x-seo-ai-visibility`

1. Sign up at [app.dataforseo.com](https://app.dataforseo.com)
2. Get credentials: Settings → API Access
3. Create auth file:

```bash
mkdir -p ~/.config/dataforseo
echo -n "your-email:your-password" | base64 > ~/.config/dataforseo/auth
chmod 600 ~/.config/dataforseo/auth
```

4. Verify:

```bash
curl -s -X POST "https://api.dataforseo.com/v3/dataforseo_labs/google/keyword_suggestions/live" \
  -H "Authorization: Basic $(cat ~/.config/dataforseo/auth)" \
  -H "Content-Type: application/json" \
  -d '[{"keyword": "test", "limit": 1}]' | jq '.status_code'
# Returns 20000 = success
```

## Uninstallation

Just delete the cloned directory:

```bash
rm -rf /path/to/30x-seo
```

## Troubleshooting

### "Skill not found" error

Make sure you're running Claude Code from the repo directory, or the parent directory containing the repo.

### DataForSEO auth errors

Check your credentials:

```bash
cat ~/.config/dataforseo/auth | base64 -d
# Should output: your-email:your-password
```

### Permission errors on Unix

Make sure scripts are executable:

```bash
chmod +x scripts/*.py
chmod +x hooks/*.py
chmod +x hooks/*.sh
```
