# EmojiOne SVGinOT Font
A color and B&W Emoji SVGinOT font built primarily from [Emoji One][1] artwork
including full support for [skin tone modifiers][2] and [country flags][3].

The font works in all operating systems, but will *currently* show color
emoji in Mozilla Firefox and Mozilla Thunderbird only. Regular B&W Emoji are
included for backwards compatibility everywhere else.

[1]: http://emojione.com/
[2]: http://www.unicode.org/reports/tr51/#Diversity
[3]: http://www.unicode.org/reports/tr51/#Flags

## Examples

## What is SVGinOT?
*SVG in Open Type* is the new standard for color OpenType and Open Font Format
fonts [adopted by the W3C on January 27th 2016][4] created by Adobe and Mozilla.
It allows font creators to embed complete SVG files within a font enabling full
color and even animations. There are more details in the [SVGinOT proposal][5].

SVGinOT Demos (Firefox only):
* https://www.adobe.com/devnet-apps/type/svgopentype.html
* https://hacks.mozilla.org/2014/10/svg-colors-in-opentype-fonts/

[4]: https://www.w3.org/community/svgopentype/2016/01/27/opentype-spec-adopts-svg-in-opentype-proposal/
[5]: https://www.w3.org/2013/10/SVG_in_OpenType/

## Usage (Linux)
1. Store the font file in your `~/.fonts/` directory.
2. Create a font config directory:
```sh
mkdir -p `~/.config/fontconfig/`
```

3. Override your defaults by creating a `fonts.conf`
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
  <!-- Generic name aliasing -->
  <alias>
    <family>sans-serif</family>
    <prefer>
      <family>EmojiOne SVGinOT</family>
    </prefer>
  </alias>
  <alias>
    <family>serif</family>
    <prefer>
      <family>EmojiOne SVGinOT</family>
    </prefer>
  </alias>
</fontconfig>
```

## Building
The build process has only been tested on Ubuntu Linux.

Overview:
1. B&W SVGs are generated on-the-fly from the color SVGs
2. The B&W SVGs are imported based on their filename to create either regular
   glyphs or ligature glyphs.
3. The color SVGs are imported to override both types of glyphs.

Required applications:
* Inkscape
* Imagemagick
* mkbitmap
* potrace
* FontTools
* FontForge
* SMFBuild (created for this project!)
* make

Run: `make`

*I am happy with the resulting glyphs, but if you have ideas about making
them look even better? Let me know! I am not a font building professional and
only recently learned how to do all of this. So, it may be terribly wrong.* 😋

## Licenses

### Artwork
* Applies to SVG files
* License: Creative Commons Attribution 4.0 International
* Human Readable License: http://creativecommons.org/licenses/by/4.0/
* Complete Legal Terms: http://creativecommons.org/licenses/by/4.0/legalcode

### Source Code
* Applies to everything else
* License: MIT
* Complete Legal Terms: http://opensource.org/licenses/MIT


### Emoji One License
The SVG files of the [Emoji One](http://emojione.com/) project are modified to
create the fallback emoji glyphs and used as-is for the SVGinOT color glyphs.

* Source: https://github.com/Ranks/emojione
* Art License: Creative Commons Attribution 4.0 International

Please review the specific attribution requirements for commercial use of
Emoji One icons: http://emojione.com/licensing/
