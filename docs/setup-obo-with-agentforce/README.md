# Setup On Behalf Of (OBO) with Agentforce

A step-by-step walkthrough for wiring a **v2 agent network broker** to call an
**Agentforce agent on behalf of the end user** — so the Agentforce session runs
as the human who started the conversation, not as a shared service account.

Identity is propagated with an OAuth 2.0 Token Exchange ([RFC 8693](https://datatracker.ietf.org/doc/html/rfc8693))
enforced at the **Flex Gateway On-Behalf-Of (OBO) policy** sitting in front of
the Agentforce agent. The broker forwards the end user's token; the gateway
swaps it for a Salesforce-scoped user token before the request reaches
Agentforce. No agent code changes are required.

## Prerequisites

This guide picks up where the Agent Network Quickstart leaves off. Complete
Quickstart **Phases 0–4** first — accounts, environment, the Salesforce link,
and mocked dependencies:

1. [Phase 0 — Prerequisites](../quickstart/00-prerequisites.md)
2. [Phase 1 — Account Setup](../quickstart/01-account-setup.md)
3. [Phase 2 — Environment Setup](../quickstart/02-environment-setup.md)
4. [Phase 3 — Link Anypoint Platform to Salesforce](../quickstart/03-link-salesforce.md)
5. [Phase 4 — Set Up Mock Agents and MCP Servers](../quickstart/04-mock-agents-and-mcps.md)

## Phases

Work through them in order:

0. [Overview & Architecture](00-overview-and-architecture.md) — the browser →
   v2 broker → Flex Gateway OBO → Agentforce flow, the RFC 8693 token exchange,
   and the zero-code-change principle.
1. [Enable Agentforce & Create the Agent](01-agentforce-agent.md) — enable
   Einstein and Agentforce, create the target agent, add the optional
   "Get Current User" flow, and test the Agent API with curl.
2. [Keycloak Identity Setup](02-keycloak-setup.md) — configure the public
   (browser) and confidential (broker) OIDC clients, user client roles, and the
   JWT claims the Salesforce handler needs.
3. [Salesforce Token Exchange](03-salesforce-token-exchange.md) — add the remote
   site, deploy the Apex OBO handler, create the Token Exchange Handler and its
   Connected App, and validate the exchange.
4. [Flex Gateway OBO Policy](04-flex-gateway-obo-policy.md) — apply the
   **OAuth 2.0 OBO Credential Injection** policy on the Flex Gateway API in front
   of the Agentforce agent.
5. [Wire the v2 Broker to the Agentforce Agent](05-wire-v2-broker.md) — register
   the gateway-fronted Agentforce agent in the v2 agent network and forward the
   end user's bearer token through the broker.
6. [Validate End-to-End](06-validate.md) — call through the v2 broker with a
   user token, confirm the Agentforce session runs as the end user, and
   troubleshoot.

Screenshots for each step live in `images/`, numbered in the order they're
referenced across the guide.

## References

- [RFC 8693: OAuth 2.0 Token Exchange](https://datatracker.ietf.org/doc/html/rfc8693)
- [Salesforce: OAuth 2.0 Token Exchange](https://help.salesforce.com/s/articleView?id=sf.remoteaccess_token_exchange_configure.htm)
- [Salesforce: Token Exchange Handlers](https://help.salesforce.com/s/articleView?id=sf.remoteaccess_token_exchange_handler.htm)
- [MuleSoft: OAuth 2.0 OBO Credential Injection Policy](https://docs.mulesoft.com/gateway/latest/policies-included-obo-token-exchange)
- [Keycloak: Token Exchange](https://www.keycloak.org/securing-apps/token-exchange)

---

**Next:** [Phase 0 — Overview & Architecture](00-overview-and-architecture.md)
