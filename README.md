# fonts

Used as personal webfont CDN.

## Tools

- [Webify](https://github.com/ananthakumaran/webify)
- [ttf2woff2](https://github.com/nfroidure/ttf2woff2)
- [otf2ttf](https://github.com/awesometoolbox/otf2ttf) (Optional)
- [TTF2OTF](https://github.com/ftCLI/TTF2OTF) (Optional)

## Make your own

Fork https://github.com/xz/fonts.

```sh
git clone https://github.com/<User>/fonts
cd fonts
```

Modify `package.json` by yourself.

```sh
webify --no-eot --no-svg fontname.ttf
cat fontname.ttf | ttf2woff2 > fontname.woff2
mkdir -p serve\src\fontname
mv fontname.woff* serve\src\fontname\
touch serve\fontname.css
```

```css
@font-face {
    font-family: 'Font Name';
    src: url('src/fontname/fontname.woff2') format('woff2'),
         url('src/fontname/fontname.woff') format('woff');
    font-weight: normal;
    font-style: normal;
    font-display: swap;
}
```

```sh
git add .
git commit -m "Add fontname"
git push
```

Goto `https://github.com/<user>/fonts/releases` → Draft a new release → Choose a tag → Input a tag liked `0.0.x` → Publish release.

## Usage

Edit `style.css`:

```css
@import url("https://cdn.jsdelivr.net/gh/<user>/fonts@master/serve/fontname.css");

body {
  font-family: 'Font Name', sans-serif;
}
```