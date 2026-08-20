# Phase 4 — Flex Gateway OBO Policy

> _Draft outline — section content to be filled in._

Put a Mule Flex Gateway in front of the Agentforce agent and apply the
**OAuth 2.0 OBO Credential Injection** policy, which performs the RFC 8693 token
exchange and replaces the inbound token with a Salesforce user token.

## Contents

- [1. Prerequisites and gateway mode](#1-prerequisites-and-gateway-mode)
- [2. Where to attach the policy](#2-where-to-attach-the-policy)
- [3. Configure OBO Credential Injection](#3-configure-obo-credential-injection)

## 1. Prerequisites and gateway mode

_Outline: Flex Gateway must run in Managed or Connected mode — Local Mode does
not support OBO policies. Note the Connected App consumer credentials from
Phase 3 are needed here._

## 2. Where to attach the policy

_Outline: attach on the API instance (API Manager) that receives the A2A traffic
in front of the Agentforce agent — the API version/instance the v2 broker calls,
not a health-check-only API._

## 3. Configure OBO Credential Injection

_Outline: add the OAuth 2.0 OBO Credential Injection policy; configure the token
exchange endpoint, client credentials, scopes, and header injection so the
outbound `Authorization` carries the Salesforce user token._

---

**Next:** [Phase 5 — Wire the v2 Broker to the Agentforce Agent](05-wire-v2-broker.md)
