<p align="center"><img src="icons/icon-192.png" width="96" height="96" alt="Ponder icon"></p>

# Ponder

Swipe through random *Magic: The Gathering* cards. One card at a time, nothing else on screen.

**Open Ponder:** https://benjhuang.github.io/ponder/

## What it does

- **Swipe left** for a new random card, **swipe right** to go back. **Tap** to turn double-faced cards over.
- **Three views:** the full card, the art only, or the art with its flavor text (lore only, never rules text).
- **Filters:** color, card type, rarity, era (1990s to 2020s), format, card language (11 languages), or any [Scryfall search](https://scryfall.com/docs/syntax).
- **More art by this artist:** tap the artist's name under the art to see more of their work.
- **Slideshow:** cards change by themselves and the screen stays on. Made for a tablet or TV.
- **Share:** send a link to Ponder or to the exact card you're looking at, or show a QR code.
- **Installable:** add Ponder to your home screen and it opens full screen like an app.

On a computer: `→` or `Space` next card, `←` back, `F` flip, `V` change view, `S` slideshow, `M` menu.

## How it works

Ponder is a static web page with no server and no build step. Card data and images come live from the
[Scryfall API](https://scryfall.com/docs/api), straight from the visitor's browser, and Ponder keeps to
Scryfall's [rate limits](https://scryfall.com/docs/api/rate-limits) (2 random cards per second at most).
Fonts and the QR code library are bundled, so Ponder talks to no one but Scryfall.

Your settings are kept in your browser's local storage. There are no accounts, cookies or analytics.

| File | Purpose |
|---|---|
| `index.html` | The whole app: layout, styles and script |
| `manifest.webmanifest` | Name, colors and icons for installing |
| `sw.js` | Service worker that lets the app itself start offline |
| `icons/` | App icons |
| `fonts/` | Spectral and Figtree, with their licenses |
| `vendor/qrcode.min.js` | QR code generator |

## Run it locally

Serve the folder with any static web server, for example:

```bash
npx serve .
```

Then open the address it prints. Installing as an app needs `https://` or `localhost`.

## Host your own copy

1. Fork this repository.
2. In **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`.
3. After a minute, your copy is live at `https://YOUR-USERNAME.github.io/ponder/`.

## Credits

- Card data and images: [Scryfall](https://scryfall.com). Please follow Scryfall's
  [API guidelines](https://scryfall.com/docs/api) if you build on this.
- Fonts: [Spectral](https://fonts.google.com/specimen/Spectral) and [Figtree](https://fonts.google.com/specimen/Figtree),
  SIL Open Font License 1.1.
- QR codes: [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) by Kazuhiko Arase, MIT License.

## Legal

Ponder is unofficial fan content, permitted under the
[Wizards of the Coast Fan Content Policy](https://company.wizards.com/en/legal/fancontentpolicy).
It is not approved or endorsed by Wizards. Card images, artwork and text are property of Wizards of the Coast.
© Wizards of the Coast LLC.
