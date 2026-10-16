# The Sparrow's Baskets 舌切り雀

A Halloween trick-or-treat for grown-ups, based on the Japanese folktale *Shita-kiri Suzume* (The Tongue-Cut Sparrow).

![The Sparrow's Inn](og.png)

## How it plays

1. **Walk.** Scroll to walk through rain-soaked neon back alleys. The scene unrolls right to left like an emaki handscroll, past a neon torii, a lantern lane where one lantern is watching you, a crossroads of spider lilies and Jizō statues, and a strip of old bamboo.
2. **Pick.** At the Sparrow's Inn, two identical baskets wait for you. One holds a treat, the other holds a trick. You get one.
3. **Pack.** Choose a treat and a trick for a friend, add a note, and tie the baskets. You get a link to send.
4. **Pass it on.** Your friend walks the same alleys, picks one of your baskets, gets a reply to send back, and then packs two for someone else.

The candy is pan-Asian: White Rabbit, Hi-Chew, Botan Rice Candy, Koala's March, Matcha KitKat, and Choco Pie as treats; Wasabi KitKat, durian candy, salted plum, red ginseng, dried squid, and crunchy natto as tricks.

## How it works

It's a single static `index.html` with no build step, no backend, and no dependencies besides Google Fonts.

- The scene is drawn on a `<canvas>` with parallax layers, rain, wet-street reflections, and a few animated yokai.
- A gift is encoded into the link's hash (`#b.<base64url JSON>`), so nothing is stored anywhere. Share links are built from the page's own address, so they work wherever you host it.
- Sound (wind chimes, rain, a low hum) is generated with Web Audio and stays off until you turn it on.
- Motion is reduced when the visitor has `prefers-reduced-motion` turned on.

## Run it locally

Open `index.html` in a browser, or serve the folder:

```sh
python3 -m http.server 8000
```

## Publish with GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**, set the source to **Deploy from a branch**, and pick `main` with the `/ (root)` folder.
3. Your site will be at `https://<your-username>.github.io/sparrows-baskets/`.

For the link preview image to show up in iMessage, WhatsApp, and similar apps, change `og:image` in `index.html` to the full address, for example `https://<your-username>.github.io/sparrows-baskets/og.png`.

## Customizing

- **Candy:** edit the `TREATS` and `TRICKS` arrays near the top of the script. Each entry has a name, origin, wrapper colors, a kanji for the wrapper, and a tasting note.
- **Stops along the walk:** edit `STATIONS`. Each `x` is a position in the world, which is 8000 units long and walked from right to left.

## Credits

Based on 舌切り雀 (Shita-kiri Suzume), a traditional Japanese folktale.
