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

You can delete fonts that you don't need.

Download some fonts.

```sh
webify --no-eot --no-svg <font>.ttf
cat <font>.ttf | ttf2woff2 > <font>.woff2
mkdir -p serve\src\<font>
mv <font>.<font>.woff* serve\src\<font>\
touch serve\<font>.css
```

```
@font-face {
    font-family: 'Font Name';
    src: url('src/<font>/<font>.woff2') format('woff2'),
         url('src/<font>/<font>.woff') format('woff');
    font-weight: normal;
    font-style: normal;
    font-display: swap;
}
```

Refer to [noticia-text.css](serve/noticia-text.css) to define `font-style` or `font-weight`.

```sh
git add .
git commit -m "Add <font>"
git push
```

Goto `https://github.com/<User>/fonts/releases` → Draft a new release → Choose a tag → Input a tag liked `0.x.x` → Publish release.

## Usage

Edit `style.css`:

```css
@import url("https://cdn.jsdelivr.net/gh/<User>/fonts@master/serve/<font>.css");

body {
  font-family: 'Font Name', sans-serif;
}
```