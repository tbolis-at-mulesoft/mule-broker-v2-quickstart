# Phase 5 — Wire the v2 Broker to the Agentforce Agent

> _Draft outline — section content to be filled in._

Register the gateway-fronted Agentforce agent as a dependency of the v2 agent
network and forward the end user's bearer token from the broker through the
Flex Gateway. This replaces the v1 Slack Trusted Agent Broker path — the same
OBO exchange, driven by a v2 agent network broker instead.

## Contents

- [1. Register the Agentforce agent in the network](#1-register-the-agentforce-agent-in-the-network)
- [2. Point the connection at the Flex Gateway URL](#2-point-the-connection-at-the-flex-gateway-url)
- [3. Forward the end user's bearer token](#3-forward-the-end-users-bearer-token)
- [4. Build and publish the network](#4-build-and-publish-the-network)

## 1. Register the Agentforce agent in the network

_Outline: add the Agentforce agent to the `registry` in `agent-network.yaml`
(agent entry) so the broker can call it as a downstream agent._

## 2. Point the connection at the Flex Gateway URL

_Outline: bind the agent's `context.connections` URL to the Flex Gateway
endpoint from Phase 4 (via an `${...}` variable in `exchange.json`), so all
traffic passes through the OBO policy._

## 3. Forward the end user's bearer token

_Outline: the broker forwards the inbound user token (Keycloak JWT) on the
outbound call; the gateway does the exchange. Keep routing deterministic —
identity propagation is transport, not a branching decision in the broker._

## 4. Build and publish the network

_Outline: build and publish the network with the CLI for Agent Fabric plugin
(mirrors Quickstart Phases 6–7); cross-reference those phases rather than
repeating them._

---

**Next:** [Phase 6 — Validate End-to-End](06-validate.md)
