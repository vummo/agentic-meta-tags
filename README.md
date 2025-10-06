# Agentic Meta Tags (AMT)

> Privacy-first metadata vocabulary for AI agents, UIs, and telemetry pipelines

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

## What is AMT?

**Agentic Meta Tags** (AMT) is a small, interoperable vocabulary for labeling public and private AI metadata used by agents, user interfaces, and data pipelines. 

Built on **PS-Lang™** (PromptScript Langauge), AMT complements existing standards like llms.txt (discovery), JSON-LD (semantic web), and OpenGraph (social) by adding behavioral signals, privacy zones, and provenance tracking for live agentic experiences.

**Agentic Meta Tags** bridge the gap between static discovery files and real-time agent behavior—enabling teams to control what agents see, track interaction quality, and preserve user consent across multi-agent workflows.

## Why AMT?

**The Problem:**
- llms.txt helps agents discover APIs and resources, but doesn't describe runtime behavior or consent
- JSON-LD provides semantic structure, but lacks privacy controls and agent-specific signals
- Modern agentic UX needs to track confidence, user feedback (RLHF), and manage visibility across zones

**AMT Provides:**
- **Privacy-aware zones** to segment public, interactive, managed, and private content
- **Behavioral signals** for confidence scoring and reinforcement learning feedback
- **Provenance tracking** for agent signatures, timestamps, and source attribution
- **Interoperability** with llms.txt, JSON-LD, and existing metadata standards

## Core Concepts

- **Zones**: `public`, `interactive`, `managed`, `private` — control where data flows
- **Visibility**: `public`, `consented`, `private` — respect user privacy boundaries
- **Signals**:
  - `confidence` (0–1) — agent's certainty in its output
  - `rl_signal` (−1…+1) — user feedback for reinforcement learning
- **Provenance**:
  - `agent_signature` — cryptographic hash identifying the agent
  - `source` — origin URI or identifier
  - `timestamp` — ISO-8601 creation time

## Minimal Examples

### Public JSON-LD (page-embedded)

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "agentic_meta": {
    "zone": "public",
    "visibility": "public",
    "confidence": 0.92,
    "agent_signature": "sha256:abc123..."
  }
}
</script>
```

### Private Stream with PS-Lang (conceptual)

```typescript
// PS-Lang zone: private stream
<$.
{
  "zone": "private",
  "visibility": "consented",
  "rl_signal": 0.8,
  "source": "user_feedback_widget"
}
.$>
```

## Quick Start

1. **Add JSON-LD to a page** — Embed AMT schema in your HTML for public metadata
2. **Map private events** — Use PS-Lang zones (or your pipeline) to tag internal agent telemetry
3. **Link in `/llms.txt`** — Add your AMT spec/examples to `/llms.txt` for agent discoverability

## Links

- **Canonical Repo**: [github.com/vummo/agentic-meta-tags](https://github.com/vummo/agentic-meta-tags)
- **Documentation**: [ps-lang.dev/agentic-meta-tags](https://ps-lang.dev/agentic-meta-tags)
- **llms.txt**: [ps-lang.dev/llms.txt](https://ps-lang.dev/llms.txt)
- **llms-full.txt**: [ps-lang.dev/llms-full.txt](https://ps-lang.dev/llms-full.txt)
- **Issues**: [github.com/vummo/agentic-meta-tags/issues](https://github.com/vummo/agentic-meta-tags/issues)
- **Discussions**: [github.com/vummo/agentic-meta-tags/discussions](https://github.com/vummo/agentic-meta-tags/discussions)

## Status & Governance

**Current Status**: Spec preview (v0.x)

AMT is actively developed and welcomes community input via GitHub Discussions and Issues. The reserved GitHub organization `agentic-meta-tags` currently mirrors/redirects to Vummo Labs repositories. As the standard matures, we aim to collaborate with standards bodies and community maintainers.

## License & Attribution

**Schema and Examples**: MIT License (or CC BY 4.0 when cited externally)
**Commercial Runtime** (signing, dashboards, managed zones): Proprietary via Journal+ platform

© 2025 **Vummo Labs LLC**. Agentic Meta Tags™ and PS-Lang™ are trademarks of Vummo Labs.

**Attribution**: Built and maintained by Vummo Labs. PS-Lang™ acknowledged as core mechanic.

## Contributing

We welcome proposals to expand the AMT vocabulary! Please:

- Use GitHub Discussions for spec ideas and questions
- Submit Issues for bugs or edge cases
- Follow example style guides (no secrets; use mock IDs like `sha256:abc123...`)
- Review [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines

## Roadmap

- **v0.2**: JSON Schema for public AMT blocks + validation tooling
- **v0.3**: Draft interop profile with llms.txt and JSON-LD
- **v0.4**: Signing guidance and provenance recommendations
- **v1.0**: Stability commitment + test corpus + reference conformance document

## Agentic Collaboration Signature

```json
{
  "project": "Agentic Meta Tags™",
  "owner": "Vummo LLC",
  "mechanic": "PS-Lang™",
  "doc": "README.md",
  "version": "0.1.0",
  "links": {
    "repo": "https://github.com/vummo/agentic-meta-tags",
    "docs": "https://ps-lang.dev/agentic-meta-tags",
    "llms_txt": "https://ps-lang.dev/llms.txt"
  },
  "meta": {
    "intent": "research",
    "scope": "technical",
    "persona": "solo_dev",
    "zone": "public",
    "confidence": 0.86
  },
  "authorship": {
    "creator": "Anton K.",
    "assistant": "Claude (Sonnet 4.5)",
    "timestamp": "2025-10-06T00:00:00Z"
  }
}
```

---

**Questions?** Open an [issue](https://github.com/vummo/agentic-meta-tags/issues) or start a [discussion](https://github.com/vummo/agentic-meta-tags/discussions). We're here to help!
