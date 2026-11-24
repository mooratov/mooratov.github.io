# Setup Instructions for mooratov.github.io

## 1. Create the GitHub repo

Go to https://github.com/new
- Name: `mooratov.github.io`
- Visibility: Public
- Do NOT initialize with README, .gitignore, or license (files already exist locally)

## 2. Push the local site

```bash
cd ~/mooratov.github.io
git init
git add .
git commit -m "Initial site"
git remote add origin git@github.com:mooratov/mooratov.github.io.git
git push -u origin main
```

GitHub Pages will automatically build the Jekyll site from the main branch.

## 3. DNS setup (Network Solutions)

Log into Network Solutions and add these DNS records for `sashamuratov.com`:

**A records** (all four):
- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

**CNAME record:**
- Host: `www`
- Points to: `mooratov.github.io`

DNS propagation can take up to 48 hours but usually resolves faster.

## 4. Enable HTTPS on GitHub

After DNS propagates:
- Go to https://github.com/mooratov/mooratov.github.io/settings/pages
- Confirm custom domain shows `sashamuratov.com`
- Check "Enforce HTTPS"

## 5. Customize content

- **Bio**: Edit `index.md`
- **Contact links**: Edit `contact/index.md` (update Google Scholar URL)
- **Add a project**: Create a new `.md` file in `_projects/` using this template:

```markdown
---
layout: project
title: Project Name
summary: One-line description shown on project cards.
tags: [Tag1, Tag2, Tag3]
github: https://github.com/mooratov/repo-name
demo: https://optional-streamlit-link.streamlit.app
---

Write the full project description here in Markdown.
```

Projects automatically appear on the home page and projects listing.

## 6. Optional: Install GitHub CLI

```bash
brew install gh
gh auth login
```

This lets Claude Code create repos, push, and manage GitHub from the terminal.

## 7. Optional: Streamlit demos

For interactive project demos:
1. Create a separate repo for the Streamlit app
2. Deploy it on https://streamlit.io/cloud (free, connects to your GitHub)
3. Add the `demo:` URL to the project's front matter in `_projects/`
