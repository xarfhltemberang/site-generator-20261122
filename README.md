# site-generator-20261122

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/xarfhltemberang/site-generator-20261122/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/xarfhltemberang/site-generator-20261122/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A fast, dependency-free ES module that builds a static site exactly like makefun-site 1.0.0 — the same output tree, byte for byte, only faster. Templates are compiled once per build into straight-line JavaScript (includes inlined, scopes resolved at compile time, the per-iteration `loop` object skipped when a loop never reads it), Markdown is rendered with bulk escaping instead of per-character escaping, and slugify has an ASCII fast path plus a cache. The reference's own front matter, template dialect, Markdown subset, slug rule and report are all reimplemented from its README and code: its front matter is not YAML, its templates are not Liquid, its Markdown is not CommonMark.

On the kit's practice set (3 generated sites, 250–480 sources each) it answers every case byte-identically to makefun-site 1.0.0, at about 3× the speed of the house baseline (median ~192 ms vs ~607 ms CPU for `run()` over the 3 cases, measured side by side on this machine). Correctness was also checked on 18 further cases drawn from the competition's own generator with fresh seeds, and on hand-built adversarial sites (template parse errors, include cycles, unicode slugs, shadowed statics, CRLF, refused front matter) — all byte-identical.

## Run it

```sh
node main.ts
```

`main.ts` reads every case from `/input/cases.json` (or `$MAKEFUN_INPUT_DIR`) and writes `/output/answers.json` (or `$MAKEFUN_OUTPUT_DIR`).

---

<sub>Entered on [make.fun](https://make.fun/?ref=1v11vwvw&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>
