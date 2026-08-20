# Example Agent Networks

Ready-to-run agent network examples for the quickstart. Each example is a
self-contained `*-network/` project with its own `README.md`:

| Example | What it demonstrates |
|---------|----------------------|
| [it-help-investigation-network](it-help-investigation-network/) | Severity triage with deterministic escalation vs. AI-driven cross-platform investigation |
| [vogue-premiere-network](vogue-premiere-network/) | Intent routing to specialist agents with a hard confirmation gate before placing orders |
| [employee-onboarding-network](employee-onboarding-network/) | Multi-agent onboarding across HR, IT, and identity systems |

Each `*-network/` project contains:

```
<name>-network/
  README.md                 # what the network does and how it was built
  agent-network.yaml        # the network topology
  brokers/<name>.agent      # the broker (AgentScript)
  exchange.json.example     # publishing descriptor + variable placeholders
  a2d-specs/                # A²D design spec(s) for the mocked dependencies
```

---

## Workflow: design the resources in A²D first, then wire the mock URLs

These networks call external agents and MCP servers (a Styling Agent, a Jira
MCP, a Customer MCP, and so on). You don't need the real backends to try the
examples — instead, use **[A²D (Agentic Asset Designer)](https://a2d-ai.com)**
to design and mock those dependencies, then point the network at the mock URLs
A²D gives you.

### 1. Import the design spec into A²D

Each example ships an A²D design spec under its `*-network/a2d-specs/` folder
(e.g. `vogue-premiere-network/a2d-specs/vogue-premiere-design-spec.json`).

In A²D, **import** that spec. It recreates every agent card and MCP server the
network depends on as mocked resources — no backend implementation required.

### 2. Deploy / activate the mocks to get their URLs

Once imported, deploy (mock) each resource in A²D. A²D exposes a **mock URL**
per resource — one per A2A agent and per MCP server the network calls.

Keep these URLs handy; they are what the network will actually talk to.

### 3. Wire the mock URLs into the network

Copy `exchange.json.example` to `exchange.json` in the `*-network/` folder and
fill in each variable with the corresponding A²D mock URL (plus your LLM
provider settings):

```bash
cd examples/vogue-premiere-network
cp exchange.json.example exchange.json
# then edit exchange.json — set each *.url to the A²D mock URL
```

The network YAML references these variables by name (for example
`${stylingAgent.url}`, `${customerMcp.url}`, `${orderMcp.url}`), so filling in
`exchange.json` is all it takes to bind the broker to the A²D mocks:

```jsonc
"variables": {
  "stylingAgent":   { "url": { "default": "https://<a2d-mock-url>/styling-agent" } },
  "availabilityAgent": { "url": { "default": "https://<a2d-mock-url>/availability-agent" } },
  "loyaltyAgent":   { "url": { "default": "https://<a2d-mock-url>/loyalty-agent" } },
  "customerMcp":    { "url": { "default": "https://<a2d-mock-url>/customer-mcp" } },
  "orderMcp":       { "url": { "default": "https://<a2d-mock-url>/order-mcp" } },
  "azureOpenAI":    { "url": { "default": "https://<your-azure-openai>/" },
                      "apiKey": { "default": "<your-api-key>" } }
}
```

> **Order matters.** Create the resources in A²D **first** — the network can't
> resolve its `${...}` URL variables until the A²D mocks exist and you've
> copied their mock URLs into `exchange.json`.

### 4. Build, publish, deploy, test

With `exchange.json` populated, follow the main quickstart guide to build,
publish, deploy, and test the network. See the repository
[README](../README.md) and the
[Agent Network Quickstart](../docs/quickstart/README.md) — in particular
[04-mock-agents-and-mcps.md](../docs/quickstart/04-mock-agents-and-mcps.md) for
the A²D step and
[06-build-agent-network.md](../docs/quickstart/06-build-agent-network.md)
onward for build and deploy.

---

`exchange.json` is intentionally not committed (it holds environment-specific
URLs and secrets) — only `exchange.json.example` is tracked. Never commit real
API keys or mock URLs tied to your account.
