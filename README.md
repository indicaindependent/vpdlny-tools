<div align="center">

# VPDLNY TOOLS

**Open-source intelligence and defence toolkit &#183; Vulnerable Defense League of NY**

[![VPDLNY](https://img.shields.io/badge/VPDLNY-Mission-8B0000?style=for-the-badge)](https://osintnet.uk)
[![Cloudflare Workers](https://img.shields.io/badge/Cloudflare_Workers-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)](https://workers.cloudflare.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Bluesky](https://img.shields.io/badge/Follow-Bluesky-0085ff?style=for-the-badge&logo=bluesky&logoColor=white)](https://bsky.app/profile/indicaindependent.bsky.social)

</div>

---

## <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/target-dark.svg"><img src="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/target-light.svg" alt="" width="22" height="22" align="top"></picture> Who we are

**VPDLNY** is a collective of technologists, artists and researchers based in New York City.

Our mission: use knowledge and information &#8212; never violence &#8212; to defend marginalized and
vulnerable people against powerful entities and institutions.

> *Information asymmetry is how the powerful stay powerful. We close the gap.*

---

## <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/stack-dark.svg"><img src="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/stack-light.svg" alt="" width="22" height="22" align="top"></picture> The tools

<div align="center">

<img src="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/charts/vpdlny-status.svg" alt="VPDLNY tools live status: twelve tools grouped by purpose with live HTTP status and measured payload size, measured 2026-09-03" width="100%">

</div>

**OSINT &amp; intelligence**

| Tool | What it does | Live | Source |
| :--- | :--- | :--- | :---: |
| **[WarHeatMap](https://warheatmap.app)** | Verified conflict events on one live map | 200 &#183; 44,662 B | [repo](https://github.com/indicaindependent/warheatmap) |
| **[EdgeIntel](https://intel.osintnet.uk)** | OSINT news aggregation at the edge | 200 &#183; 41,224 B | &#8212; |
| **[Tuck](https://tuck.osintnet.uk)** | Congressional trade disclosure, free | 200 &#183; 81,149 B | [repo](https://github.com/indicaindependent/tuck) |
| **[Skylens](https://skylens.osintnet.uk)** | Engagement-analytics observatory for Bluesky | 200 &#183; 15,478 B | [repo](https://github.com/indicaindependent/skylens) |

**Direct help**

| Tool | What it does | Live | Source |
| :--- | :--- | :--- | :---: |
| **[BizHer](https://bizher.osintnet.uk)** | Free NY LLC formation for women entrepreneurs | 200 &#183; 115,010 B | &#8212; |
| **[Crisis Lifeline Bridge](https://github.com/indicaindependent/crisis-lifeline-bridge)** | Routes a person in crisis to a REAL local agency | source | [repo](https://github.com/indicaindependent/crisis-lifeline-bridge) |
| **[VibesMom](https://github.com/indicaindependent/vibesmom)** | Mental-health support bot | source | [repo](https://github.com/indicaindependent/vibesmom) |

**Open social**

| Tool | What it does | Live | Source |
| :--- | :--- | :--- | :---: |
| **[SkyGive](https://skygive.app)** | Non-custodial Bitcoin donations, zero fee | 200 &#183; 20,171 B | [repo](https://github.com/indicaindependent/skygive) |
| **[Blueboxd](https://blueboxd.com)** | Public-domain cinema; the diary lives in your repo | 200 &#183; 166,755 B | [repo](https://github.com/indicaindependent/blueboxd) |
| **[Bluesky Campaign Engine](https://github.com/indicaindependent/bsky-campaign-engine)** | AT Protocol campaign automation | source | [repo](https://github.com/indicaindependent/bsky-campaign-engine) |

**Security**

| Tool | What it does | Live | Source |
| :--- | :--- | :--- | :---: |
| **[AXIOM Scanner](https://github.com/indicaindependent/axiom-scanner)** | Free read-only web-security scanner | source | [repo](https://github.com/indicaindependent/axiom-scanner) |
| **[CF OSINT Toolkit](https://github.com/indicaindependent/cf-osint-toolkit)** | Cloudflare Workers OSINT patterns | source | [repo](https://github.com/indicaindependent/cf-osint-toolkit) |

*Every status above was measured live on 2026-09-03, not asserted. Tools marked **source** are
repositories rather than hosted services &#8212; Crisis Lifeline Bridge, for instance, is a skill
another agent installs, not a site you visit.*

---

## <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/cpu-dark.svg"><img src="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/cpu-light.svg" alt="" width="22" height="22" align="top"></picture> Architecture

Every VPDLNY tool runs on the same stack:

    Cloudflare Workers   edge compute, zero cold start
         + D1            SQLite at the edge, primary data
         + KV            cache, flags, rate limits
         + R2            images, documents, blobs
         + Anthropic     AI reasoning
         + AT Protocol   Bluesky, open social
         + Bitcoin       sovereign payments, no middlemen

**No AWS. No GCP. No Azure. No vendor lock-in. No surveillance capitalism.**

### Deploying one yourself

Each tool deploys as a standalone Cloudflare Worker. Using
[cf-osint-toolkit](https://github.com/indicaindependent/cf-osint-toolkit) as the example:

```bash
git clone https://github.com/indicaindependent/cf-osint-toolkit
cd cf-osint-toolkit

npm install -g wrangler
wrangler login

# create the bindings that repo's README lists
wrangler d1 create osint-db
wrangler kv namespace create OSINT_CACHE

wrangler secret put ANTHROPIC_API_KEY
wrangler deploy
```

All you need is a **free-tier Cloudflare account** and an **Anthropic API key**.

---

## <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/bolt-dark.svg"><img src="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/bolt-light.svg" alt="" width="22" height="22" align="top"></picture> Support the mission

Every tool is free at the point of use. No VC, no government funding, no strings.

[![Donate via SkyGive](https://img.shields.io/badge/Donate-donate.skygive.app-8A5CF6?style=for-the-badge&logoColor=white)](https://donate.skygive.app/)
[![Lightning](https://img.shields.io/badge/Lightning-tips@skygive.app-F7931A?style=for-the-badge&logo=lightning&logoColor=white)](https://donate.skygive.app/)

**One donation path: [donate.skygive.app](https://donate.skygive.app/)** &#8212; a sovereign
Bitcoin Lightning tips node running on our own infrastructure. Non-custodial, zero fee, no KYC,
no middleman taking a cut. Every other tip link we publish resolves here.

Lightning address **`tips@skygive.app`** works in any Lightning wallet, and
[SkyGive](https://skygive.app) is itself one of the tools listed above.

---

## <picture><source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/globe-dark.svg"><img src="https://raw.githubusercontent.com/indicaindependent/vpdlny-tools/main/assets/icons/globe-light.svg" alt="" width="22" height="22" align="top"></picture> Get involved

- Open an issue on any tool repository
- Submit a pull request &#8212; all contributions welcome
- Follow on [Bluesky](https://bsky.app/profile/indicaindependent.bsky.social)
- Join the [Discord](https://discord.osintnet.uk)

---

<div align="center">
<sub>Staten Island, NYC &#183; Founded 2026 &#183; Building for the vulnerable</sub>
</div>
