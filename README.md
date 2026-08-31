# gif-cdn

A curated collection of high-quality anime roleplay GIFs, organized by action category and ready to use in bots, apps, or anything else.

---

## Stats

| Stat | Value |
|------|-------|
| Total categories | **61** |
| Total GIFs | **682** |
| Hosted on | GitHub Raw CDN |
| Index file | [index.json](./index.json) |

---

## Direct URL pattern

```
https://raw.githubusercontent.com/faisaljs/gif-cdn/main/{category}/{n}.gif
```

Replace `{category}` with any category name and `{n}` with a number from `1` to the category's count.

---

## index.json

The [index.json](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/index.json) file at the root of this repo contains all category names and their GIF counts. Fetch it once and use it to resolve valid ranges without hardcoding anything.

```json
{
  "base_url": "https://raw.githubusercontent.com/faisaljs/gif-cdn/main",
  "total_categories": 61,
  "total_gifs": 682,
  "categories": {
    "hug": 17,
    "slap": 16,
    ...
  }
}
```

---

## Usage examples

### JavaScript

```js
async function randomGif(category) {
  const index = await fetch(
    "https://raw.githubusercontent.com/faisaljs/gif-cdn/main/index.json"
  ).then((r) => r.json());

  const count = index.categories[category];
  if (!count) throw new Error(`Unknown category: ${category}`);

  const n = Math.floor(Math.random() * count) + 1;
  return `${index.base_url}/${category}/${n}.gif`;
}

// Example
const url = await randomGif("hug");
console.log(url);
// https://raw.githubusercontent.com/faisaljs/gif-cdn/main/hug/7.gif
```

### Python

```python
import httpx
import random

def random_gif(category: str) -> str:
    index = httpx.get(
        "https://raw.githubusercontent.com/faisaljs/gif-cdn/main/index.json"
    ).json()

    count = index["categories"].get(category)
    if not count:
        raise ValueError(f"Unknown category: {category}")

    n = random.randint(1, count)
    return f"{index['base_url']}/{category}/{n}.gif"

# Example
print(random_gif("pat"))
# https://raw.githubusercontent.com/faisaljs/gif-cdn/main/pat/3.gif
```

### Fetching a specific GIF

If you already know the category and want a specific GIF, you can construct the URL directly:

```
https://raw.githubusercontent.com/faisaljs/gif-cdn/main/hug/1.gif
https://raw.githubusercontent.com/faisaljs/gif-cdn/main/slap/4.gif
https://raw.githubusercontent.com/faisaljs/gif-cdn/main/cry/11.gif
```
---

## npm package

An npm wrapper is also available if you prefer installing via a package manager.

```bash
npm install gifcdn
```

→ [npmjs.com/package/gifcdn](https://www.npmjs.com/package/gifcdn)

```js
import { random, get, list, categories } from "gifcdn";

await random("hug");        // → full URL to a random hug GIF
await get("slap", 3);       // → .../slap/3.gif
await list("cry");          // → array of all 22 cry GIF URLs
await categories();         // → ["airkiss", "angrystare", ...]
```

The package ships with TypeScript types and zero dependencies — it's a thin wrapper around the same raw CDN URLs above.

---

## Categories

All categories listed alphabetically with their GIF count, URL pattern, and a preview.

| Category | Count | URL pattern | Preview |
|----------|------:|-------------|---------|
| `airkiss` | 7 | `.../airkiss/{1..7}.gif` | ![airkiss](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/airkiss/1.gif) |
| `angrystare` | 18 | `.../angrystare/{1..18}.gif` | ![angrystare](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/angrystare/1.gif) |
| `bite` | 13 | `.../bite/{1..13}.gif` | ![bite](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/bite/1.gif) |
| `bleh` | 7 | `.../bleh/{1..7}.gif` | ![bleh](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/bleh/1.gif) |
| `brofist` | 8 | `.../brofist/{1..8}.gif` | ![brofist](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/brofist/1.gif) |
| `celebrate` | 7 | `.../celebrate/{1..7}.gif` | ![celebrate](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/celebrate/1.gif) |
| `cheers` | 6 | `.../cheers/{1..6}.gif` | ![cheers](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/cheers/1.gif) |
| `clap` | 8 | `.../clap/{1..8}.gif` | ![clap](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/clap/1.gif) |
| `confused` | 8 | `.../confused/{1..8}.gif` | ![confused](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/confused/1.gif) |
| `cool` | 4 | `.../cool/{1..4}.gif` | ![cool](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/cool/1.gif) |
| `cry` | 22 | `.../cry/{1..22}.gif` | ![cry](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/cry/1.gif) |
| `cuddle` | 20 | `.../cuddle/{1..20}.gif` | ![cuddle](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/cuddle/1.gif) |
| `dance` | 18 | `.../dance/{1..18}.gif` | ![dance](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/dance/1.gif) |
| `drool` | 10 | `.../drool/{1..10}.gif` | ![drool](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/drool/1.gif) |
| `evillaugh` | 10 | `.../evillaugh/{1..10}.gif` | ![evillaugh](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/evillaugh/1.gif) |
| `facepalm` | 5 | `.../facepalm/{1..5}.gif` | ![facepalm](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/facepalm/1.gif) |
| `handhold` | 10 | `.../handhold/{1..10}.gif` | ![handhold](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/handhold/1.gif) |
| `happy` | 11 | `.../happy/{1..11}.gif` | ![happy](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/happy/1.gif) |
| `headbang` | 8 | `.../headbang/{1..8}.gif` | ![headbang](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/headbang/1.gif) |
| `hug` | 17 | `.../hug/{1..17}.gif` | ![hug](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/hug/1.gif) |
| `kiss` | 21 | `.../kiss/{1..21}.gif` | ![kiss](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/kiss/1.gif) |
| `laugh` | 16 | `.../laugh/{1..16}.gif` | ![laugh](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/laugh/1.gif) |
| `lick` | 10 | `.../lick/{1..10}.gif` | ![lick](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/lick/1.gif) |
| `love` | 9 | `.../love/{1..9}.gif` | ![love](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/love/1.gif) |
| `mad` | 20 | `.../mad/{1..20}.gif` | ![mad](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/mad/1.gif) |
| `nervous` | 13 | `.../nervous/{1..13}.gif` | ![nervous](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/nervous/1.gif) |
| `nom` | 18 | `.../nom/{1..18}.gif` | ![nom](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/nom/1.gif) |
| `nuzzle` | 9 | `.../nuzzle/{1..9}.gif` | ![nuzzle](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/nuzzle/1.gif) |
| `nyah` | 7 | `.../nyah/{1..7}.gif` | ![nyah](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/nyah/1.gif) |
| `pat` | 18 | `.../pat/{1..18}.gif` | ![pat](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/pat/1.gif) |
| `peek` | 6 | `.../peek/{1..6}.gif` | ![peek](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/peek/1.gif) |
| `pinch` | 9 | `.../pinch/{1..9}.gif` | ![pinch](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/pinch/1.gif) |
| `poke` | 14 | `.../poke/{1..14}.gif` | ![poke](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/poke/1.gif) |
| `pout` | 17 | `.../pout/{1..17}.gif` | ![pout](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/pout/1.gif) |
| `punch` | 12 | `.../punch/{1..12}.gif` | ![punch](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/punch/1.gif) |
| `sad` | 5 | `.../sad/{1..5}.gif` | ![sad](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/sad/1.gif) |
| `scared` | 17 | `.../scared/{1..17}.gif` | ![scared](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/scared/1.gif) |
| `shout` | 9 | `.../shout/{1..9}.gif` | ![shout](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/shout/1.gif) |
| `shrug` | 3 | `.../shrug/{1..3}.gif` | ![shrug](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/shrug/1.gif) |
| `shy` | 13 | `.../shy/{1..13}.gif` | ![shy](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/shy/1.gif) |
| `sigh` | 8 | `.../sigh/{1..8}.gif` | ![sigh](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/sigh/1.gif) |
| `sip` | 10 | `.../sip/{1..10}.gif` | ![sip](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/sip/1.gif) |
| `slap` | 16 | `.../slap/{1..16}.gif` | ![slap](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/slap/1.gif) |
| `sleep` | 18 | `.../sleep/{1..18}.gif` | ![sleep](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/sleep/1.gif) |
| `slowclap` | 3 | `.../slowclap/{1..3}.gif` | ![slowclap](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/slowclap/1.gif) |
| `smack` | 16 | `.../smack/{1..16}.gif` | ![smack](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/smack/1.gif) |
| `smile` | 14 | `.../smile/{1..14}.gif` | ![smile](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/smile/1.gif) |
| `sneeze` | 4 | `.../sneeze/{1..4}.gif` | ![sneeze](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/sneeze/1.gif) |
| `sorry` | 4 | `.../sorry/{1..4}.gif` | ![sorry](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/sorry/1.gif) |
| `stare` | 16 | `.../stare/{1..16}.gif` | ![stare](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/stare/1.gif) |
| `surprised` | 14 | `.../surprised/{1..14}.gif` | ![surprised](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/surprised/1.gif) |
| `sweat` | 4 | `.../sweat/{1..4}.gif` | ![sweat](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/sweat/1.gif) |
| `thumbsup` | 6 | `.../thumbsup/{1..6}.gif` | ![thumbsup](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/thumbsup/1.gif) |
| `tickle` | 9 | `.../tickle/{1..9}.gif` | ![tickle](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/tickle/1.gif) |
| `tired` | 12 | `.../tired/{1..12}.gif` | ![tired](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/tired/1.gif) |
| `wave` | 15 | `.../wave/{1..15}.gif` | ![wave](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/wave/1.gif) |
| `wink` | 18 | `.../wink/{1..18}.gif` | ![wink](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/wink/1.gif) |
| `woah` | 8 | `.../woah/{1..8}.gif` | ![woah](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/woah/1.gif) |
| `yawn` | 9 | `.../yawn/{1..9}.gif` | ![yawn](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/yawn/1.gif) |
| `yay` | 7 | `.../yay/{1..7}.gif` | ![yay](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/yay/1.gif) |
| `yes` | 8 | `.../yes/{1..8}.gif` | ![yes](https://raw.githubusercontent.com/faisaljs/gif-cdn/main/yes/1.gif) |

---

## License

[MIT](LICENSE) &copy; 2026 [faisal](https://github.com/faisaljs)
