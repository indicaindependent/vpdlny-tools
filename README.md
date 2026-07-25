<div align="center">

# 📚 VPDLNY Tools

**VPDLNY — open-source intelligence toolkit**

[![VPDLNY](https://img.shields.io/badge/VPDLNY-Mission-8B0000?style=for-the-badge)](https://osintnet.uk)
[![Cloudflare Workers](https://img.shields.io/badge/Cloudflare_Workers-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)](https://workers.cloudflare.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Bluesky](https://img.shields.io/badge/Follow-Bluesky-0085ff?style=for-the-badge&logo=bluesky&logoColor=white)](https://bsky.app/profile/indicaindependent.bsky.social)

</div>

---

## Who We Are

**VPDLNY** is a collective of technologists, artists, and researchers based in New York City.

Our mission: use knowledge and information — never violence — to defend marginalized and vulnerable people against powerful entities and institutions.

> *Information asymmetry is how the powerful stay powerful. We close the gap.*

---

## Our Tools (All Open Source)

| Tool | Description | Status |
|------|-------------|--------|
| [FaceHeatMap](https://faceheatmap.app) | US facial recognition contract tracker | 🟢 Live |
| [WarHeatMap](https://warheatmap.app) | Global conflict intelligence platform | 🟢 Live |
| [StraitTracker](https://tracker.warheatmap.app) | Strait of Hormuz geopolitical intelligence | 🟢 Live |
| [CapWatch Public](https://osintnet.uk) | Capitol surveillance tracker | 🟢 Live |
| [EdgeIntel](https://intel.osintnet.uk) | OSINT news aggregation platform | 🟢 Live |
| [CF OSINT Toolkit](https://github.com/indicaindependent/cf-osint-toolkit) | Cloudflare Workers OSINT patterns | 🟢 Open Source |
| [Bluesky Campaign Engine](https://github.com/indicaindependent/bsky-campaign-engine) | AT Protocol campaign automation | 🟢 Open Source |
| [VibesMom](https://github.com/indicaindependent/vibesmom) | AI mental health support bot | 🟢 Open Source |

---

## Architecture Philosophy

All VPDLNY tools are built on the same stack:

```
Cloudflare Workers  (edge compute, zero cold start)
     + D1           (SQLite at edge, primary data)
     + KV           (cache, flags, rate limits)
     + R2           (images, documents, blobs)
     + Anthropic Claude (AI reasoning)
     + AT Protocol  (Bluesky, open social)
     + Bitcoin      (sovereign payments, no middlemen)
```

No AWS. No GCP. No Azure. No vendor lock-in. No surveillance capitalism.

---

## Quick Deploy (Any Tool)

Each tool in this org deploys as a standalone Cloudflare Worker:

```bash
# 1. Clone the repo
git clone https://github.com/indicaindependent/<tool-name>
cd <tool-name>

# 2. Install Wrangler
npm install -g wrangler
wrangler login

# 3. Create required D1 / KV bindings (see each repo's README)
wrangler d1 create <db-name>
wrangler kv namespace create <kv-name>

# 4. Set secrets
wrangler secret put ANTHROPIC_API_KEY

# 5. Deploy
wrangler deploy
```

All tools require only a **Cloudflare account (free tier)** and an **Anthropic API key**.

---

## Support the Mission

All tools are free at the point of use. If you find them useful:

**₿ Bitcoin:** `bc1qyrtasy0naxauhf3yeg05ztu2x5vmx9jxjzsq2a`

---

## Get Involved

- 🐛 Open an issue on any tool repo
- 🔧 Submit a PR — all contributions welcome
- 🦋 Follow on [Bluesky](https://bsky.app/profile/indicaindependent.bsky.social)
- 💬 Join the [Discord](https://discord.com/channels/1494715843152711863)

---

<div align="center">
<sub>Staten Island, NYC | Founded 2026 | Building for the vulnerable</sub>
</div>


---

## ⚡ Support the Mission

Free, ad-free, independent — no VC, no gov funding, no strings.

[![Donate via SkyGive](https://img.shields.io/badge/💜_Donate_via_SkyGive-8A5CF6?style=for-the-badge&logoColor=white)](https://donate.skygive.app/)
[![Lightning](https://img.shields.io/badge/⚡_tips@skygive.app-F7931A?style=for-the-badge&logo=lightning&logoColor=white)](https://donate.skygive.app/)

<sub>🧡 Sovereign Lightning + on-chain via SkyGive.</sub>
