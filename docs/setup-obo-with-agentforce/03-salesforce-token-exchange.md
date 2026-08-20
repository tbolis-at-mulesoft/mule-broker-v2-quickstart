# Phase 3 — Salesforce Token Exchange

> _Draft outline — section content to be filled in._

Set up Salesforce to accept a Keycloak JWT and exchange it for a Salesforce user
token: a remote site, the Apex token-exchange handler, the Token Exchange
Handler registration, and a dedicated Connected App.

## Contents

- [1. Add a remote site setting](#1-add-a-remote-site-setting)
- [2. Deploy the Apex token exchange handler](#2-deploy-the-apex-token-exchange-handler)
- [3. Register the Token Exchange Handler](#3-register-the-token-exchange-handler)
- [4. Create the Connected App](#4-create-the-connected-app)
- [5. User provisioning](#5-user-provisioning)
- [6. Additional Connected App settings](#6-additional-connected-app-settings)
- [7. Validate the exchange](#7-validate-the-exchange)

## 1. Add a remote site setting

_Outline: allow callouts to the Keycloak host (JWKS) via Remote Site Settings._

## 2. Deploy the Apex token exchange handler

_Outline: the `KeycloakOBOHandler` Apex class — update constants, deploy;
note the key differences from an Okta-based handler._

## 3. Register the Token Exchange Handler

_Outline: create the Token Exchange Handler in Setup and point it at the Apex
class._

## 4. Create the Connected App

_Outline: activate Connected Apps if needed; create the app; basic info; enable
OAuth settings; configure policies; link the handler; capture consumer
credentials._

## 5. User provisioning

_Outline: required permissions; ensure test users exist in both Keycloak and
Salesforce (matched by email)._

## 6. Additional Connected App settings

_Outline: enable JWT-based access tokens; add the connection to the Agentforce
agent._

## 7. Validate the exchange

_Outline: get a Keycloak access token, exchange it for a Salesforce token,
inspect the claims, verify user identity, and optionally hit the Agentforce
Agent API with the exchanged token._

---

**Next:** [Phase 4 — Flex Gateway OBO Policy](04-flex-gateway-obo-policy.md)
