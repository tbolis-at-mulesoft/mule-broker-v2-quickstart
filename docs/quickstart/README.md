# Agent Network Quickstart

A step-by-step walkthrough for deploying a first example agent network on
MuleSoft's Anypoint Platform — from an empty machine to a deployed broker you
can call.

The guide is split into one file per phase — work through them in order:

1. [Prerequisites](00-prerequisites.md) — install VS Code, the Anypoint
   Extension Pack, and the CLI for Agent Fabric plugin, and confirm all of them
   are on the latest available versions.
2. [Account Setup](01-account-setup.md) — sign up for a MuleSoft free trial
   (Anypoint Platform account) and an Agentforce 360 Platform Free Trial org
   (for MuleSoft Vibes).
3. [Environment Setup](02-environment-setup.md) — confirm VS Code is ready and
   sign in to Anypoint Platform.
4. [Link Anypoint Platform to Salesforce](03-link-salesforce.md) — link the
   Salesforce org to Anypoint Platform to enable MuleSoft Vibes.
5. [Set Up Mock Agents and MCP Servers](04-mock-agents-and-mcps.md) — use a2d
   to design and mock the agents and MCP servers the network will call.
6. [Set Up Agent Network Gateways](05-set-up-agent-network-gateways.md) — grant
   the required permissions and deploy the Agent Network Gateways.
7. [Build the Agent Network](06-build-agent-network.md) — create the agent
   network project and build the agent network broker itself.
8. [Publish the Agent Network](07-publish-agent-network.md) — publish the
   completed network assets to Anypoint Exchange and verify them.
9. [Deploy the Agent Network](08-deploy-agent-network.md) — deploy the published
   network to CloudHub 2.0 and verify its running instances.
10. [Test the Agent Network Broker](09-test-agent-network-broker.md) — call the
    deployed broker and verify its investigation and escalation paths.

Screenshots for each step live in `images/`, numbered in the order they're
referenced across the guide. The A²D design specs used in Phase 4 live in
`specs/`.

---

**Next:** [Phase 0 — Prerequisites](00-prerequisites.md)
