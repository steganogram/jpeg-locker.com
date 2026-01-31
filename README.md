# JPEG Locker Website

Dark, hexagonal, carbon-fiber inspired product landing page for JPEG Locker — the steganography tool that hides encrypted messages and files inside ordinary JPEG images.

## 🛠 Tech Stack

- **Static Site Generator:** [Zola](https://www.getzola.org/)
- **Styling:** SCSS (compiled by Zola)
- **Form Handling:** [Formspree](https://formspree.io/) (or any static form service)

## 📁 Project Structure

```
jpeg-locker-site/
├── config.toml          # Zola configuration
├── content/
│   └── _index.md        # Homepage content
├── sass/
│   └── style.scss       # All styles
├── static/
│   └── images/
│       └── favicon.svg  # Site favicon
└── templates/
    ├── base.html        # Base template
    └── index.html       # Homepage template
```

## 🚀 Getting Started

### Prerequisites

Install Zola: https://www.getzola.org/documentation/getting-started/installation/

```bash
# macOS
brew install zola

# Windows
scoop install zola

# Linux (snap)
snap install zola --edge
```

### Development

```bash
# Navigate to project
cd jpeg-locker-site

# Start dev server with live reload
zola serve

# Opens at http://127.0.0.1:1111
```

### Build

```bash
# Build for production
zola build

# Output in ./public/
```

## 📧 Setting Up the Waitlist Form

1. Create a free account at [Formspree](https://formspree.io/)
2. Create a new form and get your form ID (looks like `f/xyzabc123`)
3. Replace `YOUR_FORM_ID` in `templates/index.html` (two places):
   ```html
   action="https://formspree.io/f/YOUR_FORM_ID"
   ```

### Alternative Form Services

- **Netlify Forms:** Add `data-netlify="true"` to the form tag
- **Getform.io:** Replace action URL with your Getform endpoint
- **Basin:** Replace action URL with your Basin endpoint

## 🌐 Deployment

### Netlify (Recommended)

1. Push to GitHub/GitLab
2. Connect repo to Netlify
3. Build settings:
   - Build command: `zola build`
   - Publish directory: `public`

Or use the included `netlify.toml`.

### Cloudflare Pages

1. Connect repo
2. Build settings:
   - Build command: `zola build`
   - Build output: `public`
   - Environment variable: `ZOLA_VERSION` = `0.19.1`

### Vercel

```bash
# Install Zola via package.json
npm init -y
npm install --save-dev zola

# vercel.json
{
  "buildCommand": "npx zola build",
  "outputDirectory": "public"
}
```

### GitHub Pages

Use the GitHub Actions workflow in `.github/workflows/deploy.yml` (create if needed):

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Build
        uses: shalzz/zola-deploy-action@v0.18.0
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

## 🎨 Customization

### Colors

Edit CSS variables in `sass/style.scss`:

```scss
:root {
    --bg-dark: #0a0a0b;           // Main background
    --accent: #22d3ee;             // Cyan accent
    --accent-dim: rgba(34, 211, 238, 0.15);
    // ... more
}
```

### Content

Edit text directly in `templates/index.html` or move content to `content/_index.md` with front matter.

### Domain

Update `base_url` in `config.toml`:

```toml
base_url = "https://yourdomain.com"
```

## 📝 License

MIT — Open source, just like JPEG Locker itself.

---

Built with 🔐 by the JPEG Locker team
