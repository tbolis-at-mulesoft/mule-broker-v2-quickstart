# MuleSoft Agent Network Quickstart

A step-by-step walkthrough for deploying a first example agent network on
MuleSoft's Anypoint Platform.

Read it as a website at
[tbolis-at-mulesoft.github.io/mule-broker-v2-quickstart](https://tbolis-at-mulesoft.github.io/mule-broker-v2-quickstart/).

## Guides

| Guide | What it covers |
|-------|----------------|
| [Agent Network Quickstart](docs/quickstart/README.md) | Ten phases, from installing VS Code to calling a broker deployed on CloudHub 2.0 |
| [Setup On Behalf Of (OBO) with Agentforce](docs/setup-obo-with-agentforce/README.md) | Wire a v2 broker to call an Agentforce agent as the end user, via Flex Gateway OBO token exchange |

Each guide lives in its own folder under `docs/`, with its screenshots and
specs alongside it.

## Examples

Ready-to-run agent network examples live in [examples/](examples/). Start with
the [examples README](examples/README.md) — it explains how to design and mock
the required resources in A²D first, then wire the mock URLs into each network.

## References

- [MuleSoft free trial signup](https://anypoint.mulesoft.com/login/signup)
- [Building Agent Networks for Agent Fabric](https://docs.mulesoft.com/agent-network/latest/af-agent-networks)
- [CLI for Agent Fabric Plugin](https://docs.mulesoft.com/anypoint-cli/latest/agent-fabric)
  — `agent-network` command reference
  ([latest plugin version on npm](https://www.npmjs.com/package/mulesoft-anypoint-cli-agent-fabric-plugin))
- [A²D — Agentic Asset Designer](https://a2d-ai.com) — design and mock the
  agents and MCP servers used by the example agent network.
