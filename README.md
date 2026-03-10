# Soochang Lee — Personal Homepage & Blog

Personal academic homepage and blog for Soochang Lee, graduate student in High Energy Physics — Theory (HEP-th).

**Live site:** [https://soo-chang-lee.github.io/](https://soo-chang-lee.github.io/)

Built with [Hugo](https://gohugo.io/) and a custom minimal dark theme with [KaTeX](https://katex.org/) for LaTeX math rendering.

---

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Static site generator | [Hugo](https://gohugo.io/) v0.124+ |
| Math rendering | [KaTeX](https://katex.org/) (inline `$...$` and display `$$...$$`) |
| Theme | Custom `minimal-dark` (dark background, clean typography) |
| Deployment | GitHub Actions → GitHub Pages (+ Netlify as fallback) |
| Content | Markdown files in `content/posts/` |

---

## Local Development

### Prerequisites

Install Hugo Extended (v0.124.1+):

```bash
# macOS
brew install hugo

# Linux — download binary from https://github.com/gohugoio/hugo/releases
# Windows — see https://gohugo.io/installation/windows/
```

### Run Locally

```bash
git clone https://github.com/Soo-Chang-Lee/Soo-Chang-Lee.github.io.git
cd Soo-Chang-Lee.github.io
hugo server -D
```

Open [http://localhost:1313](http://localhost:1313) in your browser.

---

## Writing a New Blog Post

1. Create a new Markdown file in `content/posts/`:

```bash
hugo new posts/my-new-post.md
```

Or manually create `content/posts/my-new-post.md` with this front matter:

```yaml
---
title: "My Post Title"
date: 2024-06-01
tags: ["QFT", "string theory"]
summary: "A brief summary of the post for the listing page."
---

Your content here. LaTeX math works out of the box:

Inline math: $E = mc^2$

Display math:
$$\mathcal{L} = -\frac{1}{4}F_{\mu\nu}F^{\mu\nu}$$
```

2. Save the file and push to `main` — GitHub Actions will automatically build and deploy.

---

## LaTeX / Math Usage

KaTeX is pre-configured. Use standard LaTeX delimiters:

| Type | Syntax | Example |
|------|--------|---------|
| Inline math | `$...$` | `$E = mc^2$` |
| Display math | `$$...$$` | `$$\int \mathcal{D}\phi\, e^{iS}$$` |
| Display (alt) | `\[...\]` | `\[G_{\mu\nu} = 8\pi G T_{\mu\nu}\]` |

---

## Deployment

### GitHub Pages (Primary)

The site deploys automatically via GitHub Actions on every push to `main`.

**First-time setup:**
1. Go to **Settings → Pages** in your GitHub repository.
2. Under **Source**, select **GitHub Actions**.
3. Push to `main` — the workflow in `.github/workflows/hugo.yml` will build and deploy.

### Netlify (Fallback)

1. Connect your GitHub repository to [Netlify](https://netlify.com).
2. The `netlify.toml` in the root handles build configuration automatically.

---

## Customization

### Update Your Links

Edit `hugo.toml` and update the `[params]` section with your actual profile URLs:

```toml
[params]
  github  = "https://github.com/your-username"
  email   = "mailto:your-email@institution.edu"
  arxiv   = "https://arxiv.org/search/?searchtype=author&query=Lee+S"
  inspire = "https://inspirehep.net/authors/your-id"
  scholar = "https://scholar.google.com/citations?user=your-id"
```

### Theme & Styles

Custom styles are in `themes/minimal-dark/static/css/style.css`. CSS variables at the top of the file control colors, fonts, and spacing.

---

## Site Structure

```
content/
  _index.md           # Homepage / About content
  posts/
    _index.md         # Blog section description
    hello-world.md    # Sample post with LaTeX examples
themes/
  minimal-dark/
    layouts/          # HTML templates
    static/css/       # CSS styles
.github/
  workflows/
    hugo.yml          # GitHub Actions deployment workflow
hugo.toml             # Hugo configuration
netlify.toml          # Netlify deployment configuration
```

