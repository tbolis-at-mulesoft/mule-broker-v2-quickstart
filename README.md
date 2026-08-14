# mule-broker-v2-quickstart

A step-by-step walkthrough for deploying a first example agent network on
MuleSoft's Anypoint Platform.

## Getting started

The guide is split into one file per phase — work through them in order:

1. [Prerequisites](docs/00-prerequisites.md) — install VS Code and the
   Anypoint Extension Pack.
2. [Account Setup](docs/01-account-setup.md) — sign up for a MuleSoft free
   trial (Anypoint Platform account) and a Salesforce Developer Edition org
   (for MuleSoft Vibes).
3. [Environment Setup](docs/02-environment-setup.md) — confirm VS Code is
   ready and sign in to Anypoint Platform.
4. [Link Anypoint Platform to Salesforce](docs/03-link-salesforce.md) — link
   the Salesforce org to Anypoint Platform to enable MuleSoft Vibes.
5. [Set Up Mock Agents and MCP Servers](docs/04-mock-agents-and-mcps.md) — use
   a2d to design and mock the agents and MCP servers the network will call.
6. [Set Up Agent Network Gateways](docs/05-set-up-agent-network-gateways.md) —
   grant the required permissions and deploy the Agent Network Gateways.
7. [Build the Agent Network](docs/06-build-agent-network.md) — create the
   agent network project and build the agent network broker itself.
8. [Publish the Agent Network](docs/07-publish-agent-network.md) — publish the
   completed network assets to Anypoint Exchange and verify them.
9. [Deploy the Agent Network](docs/08-deploy-agent-network.md) — deploy the
   published network to CloudHub 2.0 and verify its running instances.
10. [Test the Agent Network Broker](docs/09-test-agent-network-broker.md) —
    call the deployed broker and verify its investigation and escalation paths.

Screenshots for each step live in [docs/images/](docs/images/), numbered in
the order they're referenced across the guide.

## References

- [MuleSoft free trial signup](https://anypoint.mulesoft.com/login/signup)
- [Building Agent Networks for Agent Fabric](https://docs.mulesoft.com/agent-network/latest/af-agent-networks)
- [A²D — Agentic Asset Designer](https://a2d-ai.com) — design and mock the
  agents and MCP servers used by the example agent network.
