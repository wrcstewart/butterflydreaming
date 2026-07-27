# butterflydreaming

Static landing page for **ButterflyDreaming**, served via GitHub Pages at
[**butterflydreaming.org**](https://butterflydreaming.org).

## What this is

One HTML file (`index.html`) — a single-column poetic landing page in the
site's dark-amber palette. Introduces the project, shows a Development-
status panel (Done / To do), a Connection-status line with a coloured dot,
and the primary CTA into the graph app plus a feedback email.

Sibling repo, not related to
[`butterflydreaming_graphviewer1`](https://github.com/wrcstewart/butterflydreaming-graphviewer1)
except by subject.

## Deployment

| Piece | Where |
| --- | --- |
| Repo | `github.com/wrcstewart/butterflydreaming` (public, `main`) |
| Live URL | `https://butterflydreaming.org` |
| GitHub URL | `https://wrcstewart.github.io/butterflydreaming/` |
| DNS | 4 apex A records at Hostinger → `185.199.108-111.153` |
| Custom domain | `CNAME` file in repo root pins to `butterflydreaming.org` |
| TLS | Let's Encrypt via GitHub Pages, HTTPS enforced, auto-renews |

## Updating

1. Edit `index.html`.
2. `git commit && git push`.
3. GitHub rebuilds in ~30 seconds and republishes.

### Frequent updates

**Development status** (Done / To do) — plain text inside the two
`.status__value` spans.

**Connection status** — two things must change together:

1. The modifier class on the label:
   - `status__label--live` — green dot, "Online now"-style text
   - `status__label--intermittent` — amber dot, "Intermittent…"
   - `status__label--offline` — red dot, "Offline till <date>"
2. The `.status__body` text below it.

**Updated stamp** — dd/mm/yyyy in the `.status__stamp` span.

## DNS setup (for reference)

Hostinger's DNS zone for `butterflydreaming.org`:

```
A     @    185.199.108.153    3600
A     @    185.199.109.153    3600
A     @    185.199.110.153    3600
A     @    185.199.111.153    3600
CNAME www  butterflydreaming.org  300      # pre-existing, kept
```

MX / other records untouched — GitHub Pages only serves ports 80/443, so
mail routing is independent.
