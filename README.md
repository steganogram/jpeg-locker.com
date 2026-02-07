# JPEG Locker Website

Dark, hexagonal, carbon-fiber inspired product landing page for JPEG Locker — the steganography tool that hides encrypted messages and files inside ordinary JPEG images.

## Tech Stack

- **Static Site Generator:** [Zola](https://www.getzola.org/)
- **Styling:** SCSS (compiled by Zola)
- **Form Handling:** [Web3Forms](https://web3forms.com/)
- **Hosting:** GitHub Pages

## Project Structure

```
jpeg-locker.com/
├── config.toml          # Zola configuration
├── content/
│   └── _index.md        # Homepage content
├── sass/
│   └── style.scss       # All styles
├── static/
│   └── images/          # Static assets
├── templates/
│   ├── base.html        # Base template
│   ├── index.html       # Homepage template
│   └── macros.html      # Reusable components
└── .github/
    └── workflows/
        └── deploy.yml   # GitHub Pages deployment
```

## Getting Started

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

## Waitlist Form

The waitlist form uses [Web3Forms](https://web3forms.com/) — free, unlimited submissions, no backend required.

The access key is configured in `config.toml`:

```toml
[extra]
web3forms_key = "your-access-key"
```

The form component is defined in `templates/macros.html` and used in `templates/index.html`.

## Deployment

The site deploys automatically to GitHub Pages on push to `main` via `.github/workflows/deploy.yml`.

### Setup GitHub Pages

1. Go to repo Settings → Pages
2. Set Source to "GitHub Actions"
3. Push to `main` — the workflow handles the rest

## Customization

### Colors

Edit CSS variables in `sass/style.scss`:

```scss
:root {
    --bg-dark: #0a0a0b;
    --accent: #22d3ee;
    --accent-dim: rgba(34, 211, 238, 0.15);
}
```

### Content

Edit text in `templates/index.html`. Reusable components live in `templates/macros.html`.

### Domain

Update `base_url` in `config.toml`:

```toml
base_url = "https://yourdomain.com"
```

## License

MIT — Open source

---

Built with privacy in mind by the JPEG Locker team
