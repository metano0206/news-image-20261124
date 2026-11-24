# news-image-20261124

[![make.fun · news-image-20261124](https://make.fun/badge/news-image-20261124.svg)](https://make.fun/bounty/news-image-20261124?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261124)
[![rank](https://make.fun/badge/news-image-20261124/metano0206/news-image-20261124/rank.svg)](https://make.fun/bounty/news-image-20261124/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261124)
[![reward](https://make.fun/badge/news-image-20261124/metano0206/news-image-20261124/reward.svg)](https://make.fun/bounty/news-image-20261124?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261124)

**The World on Tuesday 24 November 2026, in one picture.** A Python 3.13 program (standard library only) that draws a one-page newspaper poster summing up the day's world news, and writes it to `/output/entry.png`. No network, no clock, no randomness: it runs twice and writes the same bytes both times.

The day's six stories, as reported on 24 November 2026:

- **Ukraine** — Russian strikes around Kyiv killed at least 14; a five-storey home collapsed in Dymer (AFP, AP, Reuters).
- **Business** — Nvidia reinstated Jensen Huang as CEO 11 days after he quit, under pressure from President Trump; shares leapt 31% (Reuters).
- **Climate** — The COP31 talks in Antalya, Türkiye, collapsed with no deal after the EU rejected a final text that dropped fossil fuels (SCMP).
- **America** — Democrats won 258 House seats, their biggest majority since 1992 (SCMP).
- **Indonesia** — At least 24 dead in the Banten candy factory fire as rescuers recovered more bodies (AP, Reuters via Arab News and the Manila Times).
- **Also today** — US states sued Elon Musk's companies over sexualised images made by the Grok AI chatbot (AP).

How it works: `main.py` holds the whole entry. The day's news lives in one clearly marked NEWS DATA block at the top of the file (date line, lead story, four panel stories, one ticker line); below it sits a small software printing press — a hand-authored 5x7 bitmap font, scanline shapes and drawn scenes (a Kyiv skyline at night, a microchip, a warming globe, the US Capitol, a burning factory), rendered at twice size and averaged down for smooth edges, then encoded as a PNG with zlib.

## Run it

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out python3 main.py
```

Without `MAKEFUN_OUTPUT_DIR` the program writes to `/output/entry.png`, as the grader expects. The image is 1024 by 1024 pixels, well under the 1 MiB cap, and takes about two seconds to draw.

License: MIT (see LICENSE).
