# FractiSI

### Tiny Footprint Multi-Agent · one shared world · many agents

**Pre-revenue frontier AI lab** · product family powered by **Tiny Gateway™**

[![Live](https://img.shields.io/badge/live-fractisi.vercel.app-0b1424)](https://fractisi.vercel.app)
[![Product](https://img.shields.io/badge/product-Multi--Agent-c9a227)](https://fractisi.vercel.app/product/)
[![Paper](https://img.shields.io/badge/paper-Multi--Agent-0b1424)](https://fractisi.vercel.app/library/papers/tiny-footprint-multi-agent/)
[![Kit](https://img.shields.io/badge/kit-Workstation-444)](https://github.com/FractiAI/tiny-footprint-workstation)
[![Lab](https://img.shields.io/badge/lab-empirical%20suite-444)](https://github.com/FractiAI/tiny-oracle-lob-pilot)

---

## What FractiSI ships

**Tiny Footprint Multi-Agent** is the flagship product.

Agent fleets — tools, workers, simulators, copilots — share one organizational context (policies, maps, corpora, world state). Today’s default is expensive: **copy that world into every agent**. Compression shrinks each copy; it does not remove the copies.

Tiny Footprint Multi-Agent registers the shared world once, keeps per-agent deltas, and reconstructs views on demand. **DRAM concurrency** is the engine inside — more agents in the same memory budget. Network fan-out and durable template stores are later adapters, not separate diluted SKUs.

| | Without Tiny Footprint | With Tiny Footprint Multi-Agent |
|--|------------------------|--------------------------------|
| Shared context | Reprinted per agent | Registered once |
| Per-agent state | Full world + local | Compact deltas |
| Goal | — | Less resident memory · higher agent density |

---

## Live site map

This repository is the **static commercial site** deployed to [fractisi.vercel.app](https://fractisi.vercel.app).

| Path | Surface |
|------|---------|
| `/` | Home — *One shared world. Many agents.* |
| `/product/` | Tiny Footprint Multi-Agent product page |
| `/research/` | Research program + open evaluation |
| `/library/` | Papers index |
| `/library/papers/tiny-footprint-multi-agent/` | Flagship Multi-Agent paper |
| `/open/` | Why we stay open |
| `/company/` | Company |
| `/recruit/` | Founding executive recruit |

---

## Evidence (labeled)

From the Multi-Agent empirical suite ([tiny-oracle-lob-pilot](https://github.com/FractiAI/tiny-oracle-lob-pilot) · `npm run multi-agent` · `npm run shine`):

| Evidence | Number | Meaning |
|----------|-------:|---------|
| Smaller-world shared pack vs naive copies | **~42%** residual after gzip | Compression alone leaves a large cross-copy tax |
| Lower shared structure | **~32%** after gzip | Still meaningful when agents diverge more |
| Sweep median (world-dominated) | **~98%** residual after gzip | When world ≫ per-agent state |
| Selective nested coarse-only task | **~99.5%** less runtime bytes | Nested vectors as DRAM/runtime win |
| Flagship 256 agents · large world | **~99%** resident proxy cut · **≫10×–1000×** density arithmetic | Lab proxies — not live HBM attestation |

Speakable line:

> One shared world for many agents — about **40%+ less** duplicated shared-context footprint after gzip in smaller-world labs, and much larger cuts when the world dominates — with a path to order-of-magnitude more concurrent agents in a fixed DRAM budget.

Always keep the after-gzip / lab-proxy qualifier in diligence rooms.

---

## One engine · three deployment surfaces

| Edition | Who | Where |
|---------|-----|-------|
| **Local (Workstation)** | Developers & researchers | Your IDE / workstation — Community free |
| **Server** | Enterprises | Company GPU / agent hosts |
| **Cloud** | Hyperscale / GPU clouds | Provider infrastructure |

- **Workstation kit:** [github.com/FractiAI/tiny-footprint-workstation](https://github.com/FractiAI/tiny-footprint-workstation)
- **Empirical suite + paper source:** [github.com/FractiAI/tiny-oracle-lob-pilot](https://github.com/FractiAI/tiny-oracle-lob-pilot)

```bash
git clone https://github.com/FractiAI/tiny-footprint-workstation.git
cd tiny-footprint-workstation
node scripts/tiny.mjs doctor
node scripts/tiny.mjs install
node scripts/tiny.mjs demo
node scripts/tiny.mjs benchmark
node scripts/tiny.mjs report
```

---

## Repository layout

```
fractisi/
├── index.html          ← home
├── product/            ← Tiny Footprint Multi-Agent
├── research/
├── library/papers/     ← including tiny-footprint-multi-agent/
├── open/
├── company/
├── recruit/
├── css/
├── media/
└── vercel.json
```

Static HTML. Deploy with Vercel (project root = this repo). Clean URLs + trailing slashes via `vercel.json`.

---

## Honesty

- Pre-revenue lab. Lab receipts are **not** CapEx guarantees, **not** production LangGraph/AutoGen bake-offs, **not** GPU HBM attestations.
- Tiny Footprint Multi-Agent is **not** a media codec and **not** a general “beat zstd on any SQL table” product.
- Operator attribution for research surfaces: SynthOBS Autonomous Agent · Syntheverse Sandbox.

---

## Contact

- Validation / shared results: **valetpru@gmail.com**
- Recruit: [/recruit/](https://fractisi.vercel.app/recruit/)

→ ∞^∞
