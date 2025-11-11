# R7 Creative Documentation

This repository contains the documentation site for R7 Creative, built with [Hugo](https://gohugo.io/) and the [Hugo Book](https://github.com/alex-shpak/hugo-book) theme.

## 🚀 Quick Start

### Prerequisites
- [Hugo Extended](https://gohugo.io/installation/) (v0.139.3 or later)
- Git

### Local Development

1. Clone this repository with submodules:
```bash
git clone --recursive https://github.com/grobenmarketing/r7creative-docs.git
cd r7creative-docs
```

If you already cloned without `--recursive`, initialize the theme submodule:
```bash
git submodule update --init --recursive
```

2. Run the Hugo development server:
```bash
hugo server -D
```

3. Open your browser to `http://localhost:1313`

### Building for Production

```bash
hugo --gc --minify
```

The site will be generated in the `public/` directory.

## 📁 Project Structure

```
.
├── content/
│   └── docs/          # Documentation content
│       ├── 00-overview/
│       ├── 01-sales/
│       ├── 02-marketing/
│       ├── 03-production/
│       ├── 04-management/
│       ├── 05-finance/
│       └── 06-human-resources/
├── themes/
│   └── hugo-book/     # Hugo Book theme (submodule)
├── static/            # Static assets
├── layouts/           # Custom layout overrides
├── hugo.toml          # Hugo configuration
├── netlify.toml       # Netlify deployment configuration
└── README.md
```

## 🌐 Deployment

This site is configured for automatic deployment on [Netlify](https://www.netlify.com/).

### Netlify Setup

1. Connect your repository to Netlify
2. Netlify will automatically detect the `netlify.toml` configuration
3. The site will build and deploy automatically on every push to the main branch

The `netlify.toml` file includes:
- Hugo version specification (v0.139.3)
- Build command configuration
- Deploy preview settings
- Security headers

## 📝 Adding Content

To add new documentation:

1. Create a new markdown file in the appropriate section under `content/docs/`
2. Add front matter to your markdown file:

```yaml
---
title: "Your Page Title"
weight: 1
---
```

3. Write your content using Markdown
4. Commit and push your changes

## 🎨 Theme Customization

The Hugo Book theme can be customized through:
- `hugo.toml` - Site-wide configuration
- `layouts/` - Custom layout overrides
- `static/` - Custom CSS, JavaScript, and images

Refer to the [Hugo Book documentation](https://github.com/alex-shpak/hugo-book) for more details.

## 📚 Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [Hugo Book Theme](https://github.com/alex-shpak/hugo-book)
- [Netlify Documentation](https://docs.netlify.com/)

## 📄 License

This documentation is proprietary to R7 Creative.
