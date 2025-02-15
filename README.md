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

## Table

font-family | source | license | @import
:-|:-|:-|:-
Sarasa Mono SC | [github](https://github.com/be5invis/Sarasa-Gothic) | [![](https://img.shields.io/github/license/be5invis/Sarasa-Gothic)](https://github.com/be5invis/Sarasa-Gothic/blob/main/LICENSE) | `sarasa-mono-sc.css`
Huiwen-mincho | [maoken](https://www.maoken.com/freefonts/9288.html) | See 「字体授权」 | `huiwen-mincho.css`
Fusion Kai | [github](https://github.com/lxgw/FusionKai) | [![](https://img.shields.io/github/license/lxgw/FusionKai)](https://github.com/lxgw/FusionKai/blob/main/LICENSE) | `fusion-kai-g.css`<br >`fusion-kai-t.css`<br >`fusion-kai-j.css`
LXGW WenKai GB | [github](https://github.com/lxgw/LxgwWenkaiGB) | [![](https://img.shields.io/github/license/lxgw/LxgwWenkaiGB)](https://github.com/lxgw/LxgwWenkaiGB/blob/main/LICENSE.txt) | `lxgw-wenkai-gb.css`<br >`lxgw-wenkai-mono-gb.css`
Smiley Sans | [github](https://github.com/atelier-anchor/smiley-sans) | [![](https://img.shields.io/github/license/atelier-anchor/smiley-sans)](https://github.com/atelier-anchor/smiley-sans/blob/main/LICENSE) | `smiley-sans.css`
Noticia Text | [1001fonts](https://www.1001fonts.com/noticia-text-font.html) | OFL | `noticia-text.css`
EB Garamond 12 | [1001fonts](https://www.1001fonts.com/eb-garamond-font.html) | OFL | `eb-garamond-12.css`
Hittle | [github](https://github.com/cesine/hittite-font) | [GPLv2](https://github.com/cesine/hittite-font/blob/master/hittitefontguide.english0.0.2.pdf) | `hittite.css`
Markazi Text | [1001fonts](https://www.1001fonts.com/markazi-text-font.html) | OFL | `markazi-text.css`