# How to Update Your Website

## Quick Reference

After editing any file (e.g. `_bibliography/papers.bib`, `_pages/about.md`, `_config.yml`):

```bash
git add -A
git commit -m "brief description of change"
git push origin main
```

That's it. GitHub Actions will automatically build and deploy within ~1 minute.

## Common Tasks

### Add a new paper

1. Edit `_bibliography/papers.bib`
2. Add an entry at the appropriate position (newest first). Example:

```bibtex
@inproceedings{author2026keyword,
      title={Paper Title},
      author={First Author and Second Author},
      abbr={VENUE},
      year={2026},
      month={July},
      selected={true},
      booktitle={Full Venue Name (ABBR)},
      paper={https://arxiv.org/abs/XXXX.XXXXX},
      code={https://github.com/...},
}
```

3. Commit and push (commands above).

### Add a news item

1. Create a new file in `_news/`, e.g. `_news/my_news.md`:

```markdown
---
layout: post
date: 2026-04-08
inline: true
---

Your news text here.
```

2. Commit and push.

### Edit the about page

1. Edit `_pages/about.md`
2. Commit and push.

## Checking Deployment Status

- Go to: https://github.com/alvinmingsf/alvinmingsf.github.io/actions
- The latest run should show a green checkmark (success) within ~1 minute.
- If it fails, click into the run to see the build logs.

## Branch Info

- **`main`** is the only branch. All source code lives here.
- GitHub Actions (`.github/workflows/deploy.yml`) builds Jekyll and deploys automatically on every push to `main`.
