# fonts-cdn

Webfont CDN powered by GitHub + jsDelivr.

Authors: GLM-5.1🧙‍♂️, DeepSeek-V4🤡, scillidan🤡

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/{user}/{repo}@{font-id}@{version}/css/{font-id}.css">
<!-- Example -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/scillidan/fonts-cdn@sarasa-mono-sc@1.0.40/css/sarasa-mono-sc.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/scillidan/fonts-cdn@sarasa-mono-sc@1.0.40/css/sarasa-mono-sc/sarasa-mono-sc.css">
```

## Quick Start

1. **Use this template**
2. **Clone** your repo to local
3. **Add font** → `fonts/{font-id}/{Font-Name}.json`
	- Get and verify font's files by using Scoop manifest
	- The `.ttf` files and the font licenses are required
4. **Push**
5. **Build** → Actions → Release → Run workflow → `{font-id}`
6. **Preview** → Your repo → Settings → Pages → Source → `GitHub Actions`
	- Visit the Github Pages website
	- If you add new fonts, you need to modify `index.html`

## Attribute

Each font has its own license. Others is under `MIT`.