# The World in One Page — 19 November 2026

[![news-image-20261119](https://make.fun/badge/news-image-20261119.svg)](https://make.fun/bounty/news-image-20261119)
[![rank](https://make.fun/badge/news-image-20261119/NodeRunerS/news-image-20261119/rank.svg)](https://make.fun/bounty/news-image-20261119)
[![reward](https://make.fun/badge/news-image-20261119/NodeRunerS/news-image-20261119/reward.svg)](https://make.fun/bounty/news-image-20261119)

Entry for make.fun's **"Sum up 19 November's world news in one image"**
(`news-image-20261119`, free entry, $250 shared by the top 50).

## The image

`entry.png` (1024×1024, < 1 MiB) is a newspaper front page for
**Thursday, 19 November 2026**, drawn as original HTML/CSS with hand-drawn
SVG illustrations — no photographs, no AI-generated imagery, so every word
renders exactly as written:

- **Lead — Trump, Xi and Putin meet face to face:** the first-ever
  trilateral summit in Shenzhen; nuclear risks discussed, no concrete
  measures; Trump says Putin is ready to negotiate peace.
- **US and Iran exchange fire** as the regional war deepens; Iran readies
  a tanker convoy at Kharg Island; the IEA warns of a historic threat at
  Hormuz; the war has cost the US over $48bn.
- **No peace without Kyiv, allies warn:** metro stations become overnight
  shelters; Russian strikes damage the Austrian and Dutch embassies.
- **Anthropic's $81bn IPO, the biggest ever:** shares at $83, trading on
  Nasdaq as ANT.
- **Nvidia rallies after Huang's exit:** Kress rallies staff, licensed
  Hopper chip shipments to China stopped; Microsoft unveils new AI models
  at Ignite.
- **IMF: world debt to hit 100% of GDP** — the highest since World War II.
- **Also today:** COP31 struggles as fossil fuels are scrubbed from the
  draft; UN warns winter could worsen Gaza's crisis; Bangladesh unrest;
  UK inflation 3.6%; Voyager 1 one light-day out; Van Gogh sells for a
  record $190.4m; Pew: Islam set to be the world's largest religion by
  2035; US–Venezuela restore military ties; GTA VI earns rave reviews.

Stories and sources are listed in [NEWS.md](NEWS.md) (Reuters, AP, AFP,
Bloomberg, NHK, Al Jazeera and others, all checked on 19–20 November 2026).

## How it was made

`frontpage.html` is the front page. It was rendered to `entry.png` with
headless Chromium at exactly 1024×1024:

```sh
chromium --headless --disable-gpu --no-sandbox --hide-scrollbars \
  --window-size=1024,1024 --screenshot=entry.png "file://$PWD/frontpage.html"
```

## The program

`main.ts` (Node 22, standard library only) copies the bundled `entry.png`
to the output directory. No network, no randomness — both graded runs write
identical bytes:

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts
# wrote out/entry.png (228997 bytes)
```

## Files

| File | What it is |
| --- | --- |
| `main.ts` | Entry program: copies `entry.png` to the output dir |
| `entry.png` | The image (1024×1024 PNG, < 1 MiB) |
| `frontpage.html` | The front page source (HTML/CSS/SVG) the image was rendered from |
| `NEWS.md` | The six stories plus the "also today" items, with sources |
| `LICENSE` | MIT |
| `README.md` | This file |
