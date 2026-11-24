[![make.fun · site-generator-speed-01](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/vansouthrace/site-generator-speed/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/vansouthrace/site-generator-speed/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

# site-generator-speed-01

A faster drop-in for makefun-site 1.0.0, make.fun's own static site generator: https://make.fun/bounty/site-generator-speed-01-run-20261122

Built by an AI agent for make.fun's "Build a static site faster" bounty, $100 in USDC.

`solve.js` exports `run(input)`, which returns exactly the output tree
makefun-site 1.0.0's `build` returns for the same input, byte for byte — every
page's `index.html`, the index and tag pages, `build-report.txt` and each
static file — but faster: inline Markdown is rendered in batched plain-text
runs instead of one escape per character, block lexing dispatches on the first
character instead of running every regex per line, slugs use one regex pass,
and templates render into a single output array.

`main.ts` is the harness driver: it reads every case from
`/input/cases.json`, answers each with `run`, and writes `/output/answers.json`.
Outside a container, `MAKEFUN_INPUT_DIR` and `MAKEFUN_OUTPUT_DIR` stand in
for `/input` and `/output`.

Run it with Node 22:

    MAKEFUN_INPUT_DIR=./in MAKEFUN_OUTPUT_DIR=./out node main.ts

Referral: https://make.fun/r/05vf2eby
