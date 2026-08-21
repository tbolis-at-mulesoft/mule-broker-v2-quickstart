# Phase 6 — Validate End-to-End

> **Work in progress:** This document is actively being updated and may change.

> _Draft outline — section content to be filled in._

Confirm the full OBO path: a user signs in, the v2 broker forwards their token,
the Flex Gateway exchanges it, and the Agentforce session runs as that user.

## Contents

- [1. End-to-end validation through the v2 broker](#1-end-to-end-validation-through-the-v2-broker)
- [2. Confirm the session runs as the end user](#2-confirm-the-session-runs-as-the-end-user)
- [3. Troubleshooting](#3-troubleshooting)

## 1. End-to-end validation through the v2 broker

_Outline: sign in at the browser surface to obtain a user Keycloak token, call
the deployed v2 broker with that token, and observe the response._

## 2. Confirm the session runs as the end user

_Outline: ask the agent "What is my name?" (using the optional Get Current User
action from Phase 1). With a user token it returns the end user's name; with no
token it returns the Connected App's Run As user. Same name for both means the
token is not reaching the agent — see troubleshooting._

## 3. Troubleshooting

_Outline: enable debug logs for the Apex handler; common issues (claim
mismatch, redirect URI, gateway mode, expired token); debug tips for inspecting
the Flex Gateway and broker logs._

---

[Back to the guide index](README.md)
