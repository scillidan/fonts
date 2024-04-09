# fonts

Used as CDN for personal websites. See [table.md](table.md)

## Tool

- [Webify](https://github.com/ananthakumaran/webify)
- [ttf2woff2](https://github.com/nfroidure/ttf2woff2)
- [otf2ttf](https://github.com/awesometoolbox/otf2ttf) (Optional)
- [TTF2OTF](https://github.com/ftCLI/TTF2OTF) (Optional)

## Notes

Fork https://github.com/xz/fonts,

```
git clone https://github.com/username/fonts
cd fonts
```

Edit `package.json` about you. And You can delete fonts that you don't need.

Download some fonts.

```
webify --no-eot --no-svg font.ttf
cat font.ttf | ttf2woff2 > font.woff2
mkdir -p serve/src/fontdir
```

Put `font.woff` `font.woff2` into `fontdir`. (I only used `.woff` and `.woff2`.)

Create `serve/font.css`, and edit it:

```
@font-face {
    font-family: 'name';
    src: url('src/fontdir/font.woff2') format('woff2'),
         url('src/fontdir/font.woff') format('woff');
    font-weight: normal;
    font-style: normal;
    font-display: swap;
}
```

If you need use multiple `font-style` or `font-weight`, refer to [serve/noticia-text.css](serve/noticia-text.css) and [](serve/src/noticia-text) to modify the steps.

When it's all done, push it to Github.

Go https://github.com/user/fonts/releases > `Draft a new release` > `Choose a tag` > Input a tag like `1.x.x` > `Publish release`.

Finally, write something like this in `style.css`:

```css
@import url("https://cdn.jsdelivr.net/gh/username/fonts@master/serve/sarasa-mono-sc.css");

body {
  font-family: 'Sarasa Mono SC', sans-serif;
}
```

Enjoy new webfont.

`index.html` and `list.html` are not necessary, but you can also complete them.