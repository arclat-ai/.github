<div align="center">

<img src="https://raw.githubusercontent.com/arclat-ai/.github/main/profile/assets/arclat-logo.png" alt="Arclat" width="220">

# Arclat

### We build the tools that make AI agents fast, cheap, and reliable.

Arclat is a studio shipping focused developer tools for teams building AI agents.
Our tools live where engineers already work — inside the editor and the command line.

[Website](https://arclat.com) · [Relay](https://relay.arclat.com) · [LinkedIn](https://www.linkedin.com/company/arclat/) · [Instagram](https://www.instagram.com/arclat.ai/)

</div>

---

## What we're shipping

### 🟢 [Relay](https://github.com/arclat-ai/relay-mcp) — live

**Find the latency in your AI agent, before your users do.**

An open-source **MCP server + CLI** that audits AI agent and voice-agent codebases for
latency bottlenecks. It reads your real source with an AST engine, ranks issues by the
time they cost, runs a verification pass to drop false positives, and can apply fixes
directly from Claude Code.

No account. No API key. No backend — it runs entirely on your machine.

```bash
claude mcp add relay -- uvx --from relay-arclat relay-mcp
```

<sub>MCP · Claude Code · Python 3.11+ · MIT</sub>

### ⚪ In the works

We ship deliberately, one focused tool at a time. The next products for teams running
AI agents in production are in design — [details soon](https://arclat.com/coming-soon).

---

## How we build

**Built for the terminal.** Our tools plug into the editor and the shell, not another
browser tab.

**Your code stays yours.** Analysis runs locally wherever possible. We sync metadata,
never your source.

**One focused tool at a time.** We'd rather ship one product that nails a real problem
than ten that almost do.

---

## Contributing

Relay is open source and we read every issue. Start with
[CONTRIBUTING.md](https://github.com/arclat-ai/relay-mcp/blob/main/CONTRIBUTING.md),
or open a discussion if you've found agent latency our detectors miss — those reports
are the single most useful thing you can send us.

Security reports go to the process in
[SECURITY.md](https://github.com/arclat-ai/relay-mcp/blob/main/SECURITY.md), not to a
public issue.

<div align="center">
<sub>Built by the Arclat studio.</sub>
</div>
