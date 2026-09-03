# active-trackers.hosts

A personal, community-sharable blocklist of domains that were **active**
("red") against my machine in a Pi-hole / tracker dashboard.

## What this is
- A snapshot of ~110 domains flagged as **active** in a tracker dashboard.
- **Not** a "malicious software" list 

  list. It's a point-in-time capture of what was hitting *my* network.
- Format: `0.0.0.0 <domain>` (standard `hosts` / Pi-hole style).

## What "active / red" means
In the source dashboard, **red = currently connected / making requests**,
and **green = not active**. This list only contains the red entries.

## How to use it
**Pi-hole** (recommended — auto-updates):
1. Settings → Blocklists → "Add new list"
2. Paste the **raw** URL to this file (e.g.
   `https://raw.githubusercontent.com/<you>/<repo>/main/active-trackers.hosts`)
3. "Update lists" → it refreshes on every Pi-hole list update.

**Any `hosts`-based blocker:** append this file next to your other lists. Overlap with other lists is harmless.

## Caveats — read before enabling
- **Snapshot:** re-scan and re-publish periodically; domains change.
- **Functional service domains** are included and flagged with a trailing
  `# functional …` comment. Blocking them works but may degrade those
  services: `s.youtube.com`, `redirector.googlevideo.com`,
  `graph.instagram.com`, `i.instagram.com`, `xp.apple.com`, `ads.huawei.com`.
- **TO CONFIRM block:** three domains were truncated at capture time and are
  left commented out. Un-comment only after verifying each full domain:
  `rum.browser-intake-datadoghq.com`, `books-analytics-events.apple.com`,
  `analytics-api.samsunghealthcare.com`.
- `vk.com/rtg` (a URL path, not a host) is intentionally omitted; blocking
  `vk.com` would take all of VK offline.

## Disclaimer
Provided "as is", without warranty. These are publicly known service
domains; blocking them is your responsibility.

## License
CC0 1.0 Universal — public domain dedication. See `LICENSE`.