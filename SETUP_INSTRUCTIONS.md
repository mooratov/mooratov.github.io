# Setup Instructions for mooratov.github.io

## Status (as of 2026-11-24)

- [x] Repo created: https://github.com/mooratov/mooratov.github.io
- [x] Jekyll site pushed to main branch
- [x] gh CLI installed and authenticated
- [x] Custom domain: mooratov.github.io redirects to sashamuratov.com
- [ ] DNS setup at Network Solutions (site showing blank — this is likely the issue)
- [ ] HTTPS enforced on GitHub Pages
- [ ] Google Scholar link updated in contact/index.md
- [ ] Git author config set

## 1. Fix blank page — DNS setup (Network Solutions)

The site redirects to sashamuratov.com but shows blank, which likely means DNS
is not fully configured. Log into Network Solutions and ensure these DNS records
exist for `sashamuratov.com`:

**A records** (all four — these point the root domain to GitHub Pages):
- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

**CNAME record:**
- Host: `www`
- Points to: `mooratov.github.io`

DNS propagation can take up to 48 hours but usually resolves within an hour.

If DNS is already set and the page is still blank, check the GitHub Pages build:
- Go to https://github.com/mooratov/mooratov.github.io/actions
- Look for a failed "pages build and deployment" workflow
- The build log will show any Jekyll errors

## 2. Enable HTTPS on GitHub

After the site loads correctly:
- Go to https://github.com/mooratov/mooratov.github.io/settings/pages
- Confirm custom domain shows `sashamuratov.com`
- Check "Enforce HTTPS"

## 3. Set git author info

```bash
git config --global user.name "Sasha Muratov"
git config --global user.email "mooratov@gmail.com"
```

## 4. Customize content

The local repo is at `~/mooratov.github.io-repo/`.

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

After editing, push changes:
```bash
cd ~/mooratov.github.io-repo
git add .
git commit -m "Description of changes"
git push
```

## 5. Optional: Streamlit demos

For interactive project demos:
1. Create a separate repo for the Streamlit app
2. Deploy it on https://streamlit.io/cloud (free, connects to your GitHub)
3. Add the `demo:` URL to the project's front matter in `_projects/`
