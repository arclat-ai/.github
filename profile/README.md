<div align="center">

<img src="https://raw.githubusercontent.com/arclat-ai/.github/main/profile/assets/arclat-logo.png" alt="Arclat" width="96">

# Arclat

### Domain intelligence platforms & open-source developer tooling for AI agents.

Arclat builds high-impact applied AI software for complex enterprise workflows and focused open-source infrastructure for autonomous AI agents.

[Website](https://www.arclat.com) · [TenderDesk](https://tender.arclat.com) · [WebMCP](https://github.com/arclat-ai/webmcp-bridge) · [Relay](https://relay.arclat.com) · [mcpie](https://mcpie.arclat.com) · [LinkedIn](https://www.linkedin.com/company/arclat/) · [Instagram](https://www.instagram.com/arclat.ai/)

</div>

---

## Flagship Enterprise Platform

### <img src="https://raw.githubusercontent.com/arclat-ai/.github/main/profile/assets/tenderdesk-icon.png" width="24" height="24" alt="TenderDesk" valign="middle"> [TenderDesk](https://tender.arclat.com): AI Procurement & Tender Intelligence

> **Production Platform** - Built for contractors, engineering firms, and procurement teams bidding on Pakistani public contracts.

Public procurement moves fast with complex compliance rules, high non-refundable bid securities, and hundreds of daily notices scattered across federal and provincial gateways. **TenderDesk** automates the entire tender lifecycle, from portal discovery to contract award.

```
Multi-Source Ingest ──► Pass 1: Deterministic Check ──► Pass 2: AI Adjudication ──► 10-Stage Pipeline
(PPRA, EPADS, NHA)       (PEC Codes, Turnover, NTN)     (JV Scope, Past Scale)       (Discovered ➔ Awarded)
```

- **Continuous Multi-Source Ingestion:** Real-time, deduplicated notice ingestion from federal PPRA, EPADS, National Highway Authority (NHA), WAPDA, NESPAK, and provincial gateways.
- **Two-Pass Eligibility Engine:**
  - *Pass 1 (Deterministic):* Verifies non-negotiable gates: PEC category limits, annual turnover thresholds, and active NTN/tax status.
  - *Pass 2 (AI Adjudication):* Deep scope adjudication for complex Joint Venture (JV) allowances, specialist scope codes (e.g., CE-04, EE-01), and project volume match.
- **10-Stage Lifecycle Pipeline:** Tracks bids from *Discovered* → *Under Review* → *Technical Bid* → *Financial Bid* → *Submitted* → *Awarded*.
- **Native In-Engine PDF Parsing:** Native on-instance text extraction with zero token waste on text-embedded notices, plus multimodal visual extraction for scanned authority addenda.
- **Account-Level Data Isolation:** Strict multi-tenant security boundary with UUID isolation, firm document locker for compliance reuse, and private win/loss telemetry.

**[Launch TenderDesk →](https://tender.arclat.com)** &nbsp;|&nbsp; **[Explore Platform Tour →](https://www.arclat.com/products/tenderdesk)**

---

## Open-Source Agent Tooling Suite

Lightweight, focused tools for engineers building, optimizing, and securing autonomous AI agent systems.

### <img src="https://raw.githubusercontent.com/arclat-ai/.github/main/profile/assets/webmcp-icon.png" width="22" height="22" alt="WebMCP" valign="middle"> [WebMCP Bridge](https://github.com/arclat-ai/webmcp-bridge) (live)

**Headless in-page browser bridge for Claude & MCP agents.**

WebMCP connects in-page tool definitions (`window.navigator.modelContext`) directly to Claude Desktop, Claude Code, and Model Context Protocol agents. It runs a silent, headless Playwright Chromium instance over stdio JSON-RPC, transforming web applications into queryable agent tools without extensions, manual scrapers, or proprietary SDKs.

- **Zero Browser Extensions:** No unpacked extensions to sideload, no manifest permission friction, and no user profile pollution.
- **Sub-5ms Execution Latency:** Direct in-memory page evaluation via Chromium DevTools Protocol (CDP).
- **Strict Schema Enforcement:** Translates client-side tool registrations into validated JSON Schema Draft-07 with Zod validation.
- **100% Local-First:** Everything runs locally on your machine over stdio. Zero third-party telemetry, zero external servers.

```bash
# Connect Claude to any WebMCP-enabled web app
claude mcp add webmcp -- npx -y @arclat-ai/webmcp-bridge connect http://localhost:3000
```

<sub>MCP · Playwright · Chrome DevTools Protocol · Node.js 18+ · MIT</sub>

---

### <img src="https://raw.githubusercontent.com/arclat-ai/.github/main/profile/assets/relay-icon.png" width="22" height="22" alt="Relay" valign="middle"> [Relay](https://github.com/arclat-ai/relay-mcp) (live)

**Find the latency in your AI agent, before your users do.**

An open-source **MCP server + CLI** that audits AI agent and voice-agent codebases for latency bottlenecks. It inspects Python source with an AST parser, attributes wall-clock time to the exact lines of code that spend it, runs a verification pass to drop false positives, and can apply fixes directly inside Claude Code.

- **Ranked by seconds, not severity:** Fixes are sorted by recoverable wall-clock latency, so you fix the biggest bottleneck first.
- **Catches the usual suspects:** Blocking I/O inside async loops, serial tool calls that should run concurrently, unmemoized embeddings, and unbacked retries.
- **Runs entirely on your machine:** Zero external API keys, zero accounts, and zero code upload.

```bash
# Add Relay directly to Claude Code
claude mcp add relay -- uvx --from relay-arclat relay-mcp
```

<sub>MCP · Claude Code · Python 3.11+ · MIT</sub>

---

### <img src="https://raw.githubusercontent.com/arclat-ai/.github/main/profile/assets/mcpie-icon.png" width="22" height="22" alt="mcpie" valign="middle"> [mcpie](https://github.com/arclat-ai/mcpie) (live)

**npm audit for the Model Context Protocol.**

Every MCP server you connect to Claude or Cursor is third-party code running with access to your filesystem, shell, and API keys. **mcpie** scans MCP packages for tool poisoning, over-broad permissions, credential leaks, and supply-chain rug pulls before you connect them.

- **Safe static extraction:** Analyzes AST and manifest schemas without ever executing untrusted server code. Live probe mode is opt-in behind `--live`.
- **Dual-dimension scoring:** Every finding carries distinct **Severity** and **Confidence** ratings, so heuristics are never masqueraded as certainties.
- **CI/CD native:** Emits standard SARIF reports that plug straight into GitHub Code Scanning and automated pull request guards.

```bash
# Scan any MCP server or local package
npx @arclat-ai/mcpie scan
```

<sub>Node 18.17+ · Zero Runtime Dependencies · Apache-2.0</sub>

---

## How we build

- **Grounded in domain truth.** High-stakes enterprise software (like procurement) requires zero-hallucination guarantees and deterministic gates before AI adjudication runs.
- **Built for developer flow.** Developer tools belong in the terminal and editor where engineers work, not in bloated web dashboards.
- **Your data stays yours.** Enterprise records are isolated at the database layer; developer audits execute locally on your hardware.

---

## Contributing & Security

All agent tools in the suite are open source and actively maintained:

- **WebMCP**: [CONTRIBUTING.md](https://github.com/arclat-ai/webmcp-bridge/blob/main/CONTRIBUTING.md): report bridge bugs or submit protocol adaptors.
- **Relay**: [CONTRIBUTING.md](https://github.com/arclat-ai/relay-mcp/blob/main/CONTRIBUTING.md): report latency patterns our AST scanner misses.
- **mcpie**: [CONTRIBUTING.md](https://github.com/arclat-ai/mcpie/blob/main/CONTRIBUTING.md): submit security heuristics or false-positive reports.

Security vulnerability reports should be submitted following the instructions in each repository's `SECURITY.md` or emailed privately to [team@arclat.com](mailto:team@arclat.com).

<div align="center">
<sub>© Arclat. Built with purpose.</sub>
</div>
