# License Notices

This plugin bundles skills from more than one source. There is no single license for the whole
repository — check the table below before reusing a specific skill.

| Skill | License | Notes |
|---|---|---|
| `skills/adsense-content-pipeline/` | Original work for this project | No third-party code |
| `skills/content-quality-auditor/` | Apache-2.0 | Imported from [aaron-he-zhu/aaron-marketing-skills](https://github.com/aaron-he-zhu/aaron-marketing-skills) v20.1.0; see its `LICENSE` and `LOCAL-CHANGES.md` |
| `skills/geo-content-optimizer/` | Apache-2.0 | Same source; see its `LICENSE` and `LOCAL-CHANGES.md` |
| `skills/serp-markup-builder/` | Apache-2.0 | Same source; see its `LICENSE` and `LOCAL-CHANGES.md` |
| `skills/clarity/` | MIT | Includes its own `LICENSE` file |
| `skills/adsense-auditor/` | See `references/CREDITS.md` | Checklist structure adapted from a public template; policy content re-grounded in Google's own docs |
| `skills/human-web-content/` | See `references/CREDITS.md` | |
| `skills/pagewell/` | States MIT in its frontmatter | No `LICENSE` file was included upstream; confirm with the original author (ReScienceLab, https://pagewell.dev) before redistributing |
| `skills/seo-geo/` | Unknown / unattributed | No license or origin file was found upstream. Do not treat this as freely licensed until the source is confirmed |
| `agents/*.md` | Original work for this project | No third-party code |

## What this means if you use this repo

- The Apache-2.0 skills may be copied and modified, but you must keep their `LICENSE` and state
  what you changed (already done in each `LOCAL-CHANGES.md`).
- `clarity` may be copied and modified under the MIT terms in its own `LICENSE` file.
- `pagewell` and `seo-geo` have not been independently license-cleared. Treat them as
  "included for convenience, provenance unconfirmed" rather than as openly licensed, until you
  verify the source.
- The original skills and agents written for this project (`adsense-content-pipeline` and the
  four agents) have no reuse restriction from this project's side, but they reference and depend
  on the other skills above to function.

This file exists so a plugin manager or a future maintainer can see licensing status at a glance.
It is not legal advice.
