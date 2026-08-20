# Phase 2 — Keycloak Identity Setup

> _Draft outline — section content to be filled in._

Configure Keycloak as the identity provider: a public client for the browser
sign-in and a confidential client for the broker, plus the user roles and JWT
claims the Salesforce token-exchange handler needs.

## Contents

- [1. Keycloak endpoint reference](#1-keycloak-endpoint-reference)
- [2. Verify access token claims](#2-verify-access-token-claims)
- [3. Public browser client](#3-public-browser-client)
- [4. Confidential broker client](#4-confidential-broker-client)
- [5. Verify with a user token](#5-verify-with-a-user-token)

## 1. Keycloak endpoint reference

_Outline: where to find the realm endpoints (authorization, token, JWKS,
userinfo) in the Admin Console; note the `master` realm assumption._

## 2. Verify access token claims

_Outline: confirm the claims the Salesforce Apex handler will match on (e.g.
email) are present in the access token._

## 3. Public browser client

_Outline: create the public OIDC client (auth code + PKCE) for the browser
surface; set valid redirect and post-logout URIs; default scopes._

## 4. Confidential broker client

_Outline: create the confidential client the v2 broker uses; capability config;
assigned scopes; quick test._

## 5. Verify with a user token

_Outline: assign the broker client role to a test user, obtain a user token,
and inspect the access token to confirm the claims._

---

**Next:** [Phase 3 — Salesforce Token Exchange](03-salesforce-token-exchange.md)
