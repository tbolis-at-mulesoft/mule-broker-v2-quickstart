# Phase 5 — Set Up Agent Network Gateways

With Anypoint Platform linked to Salesforce and the MCP servers enabled, set
up the Agent Network Gateways the agent network will run on.

## Contents

- [1. Grant the required Anypoint Platform permissions](#1-grant-the-required-anypoint-platform-permissions)
- [2. Set up Agent Network Gateways](#2-set-up-agent-network-gateways)
  - [Anypoint Platform UI approach](#anypoint-platform-ui-approach)
  - [Command Palette approach (non-trial accounts only)](#command-palette-approach-non-trial-accounts-only)
    - [Select a Business Group](#select-a-business-group)
    - [Select an environment](#select-an-environment)
    - [Select the target space type](#select-the-target-space-type)
    - [Select the target region](#select-the-target-region)
    - [Confirm the gateway name](#confirm-the-gateway-name)
- [3. Wait for the gateway to deploy](#3-wait-for-the-gateway-to-deploy)

## 1. Grant the required Anypoint Platform permissions

Before setting up the gateways, make sure the user has the permissions listed
in the [Agent Network platform requirements](https://docs.mulesoft.com/agent-network/latest/af-get-started#platform-requirements)
docs — permissions across Runtime Manager, Anypoint Code Builder, Design
Center, API Manager, Exchange, Usage, and CloudHub 2.0.

![Anypoint Platform Requirements and Permissions table](images/42-agent-network-permissions-table.png)

In Anypoint Platform, go to **Access Management → Users**, select the user,
and click **Add Permissions**. For simplicity, rather than picking individual
permissions one by one, click **Select all** on each product category to
grant every permission, then continue through **Select Business Groups** and
**Select Environments** and scope that to just the Business Group and
environment you'll use for the agent network.

![Add Permissions dialog in Anypoint Access Management](images/43-add-permissions-dialog.png)

## 2. Set up Agent Network Gateways

### Anypoint Platform UI approach

**For trial accounts, use the Anypoint Platform UI** — the VS Code Command
Palette command doesn't work on trial accounts due to trial-related
limitations, so the UI is the go-to path here.

In Anypoint Platform, go to **Runtime Manager → Omni Gateways**, select the
**Managed Omni Gateway** tab, and click **Add Managed Omni Gateway**.

![Runtime Manager Omni Gateways page, with Add Managed Omni Gateway](images/44-runtime-manager-omni-gateways.png)

Fill out the form: **Gateway Name** (e.g. `agent-network-shared-gw`),
**Deployment Target** (region + space type, e.g. Cloudhub-US-East-2 / Shared
Space), **Release Channel** (e.g. Edge), **Version** (latest), and **Gateway
type** (e.g. Small Omni Gateway). Note: some configurations are disabled and
not customizable on trial accounts.

![Add Managed Omni Gateway form, with name, deployment target, release channel, version, and gateway type](images/45-add-managed-omni-gateway-form.png)

### Command Palette approach (non-trial accounts only)

This is an alternative to the Anypoint Platform UI approach for non-trial
accounts only. Open the Command Palette (**Cmd+Shift+P**) and run **"MuleSoft:
Set Up Agent Network Gateways..."**. The command walks through the same choices
as a series of quick-picks instead of a single form.

![Command Palette running MuleSoft: Set Up Agent Network Gateways](images/46-command-palette-setup-gateways.png)

#### Select a Business Group

Pick the Business Group to set up the gateways in — for example, the
**Salesforce** Business Group.

![Select a Business Group quick-pick](images/47-select-business-group.png)

#### Select an environment

Pick the environment to deploy the gateway to — for example, **Sandbox**.

![Select the environment quick-pick](images/48-select-environment.png)

#### Select the target space type

Pick **Shared Space** or **Private Space** for the gateway.

![Select the target space type quick-pick](images/49-select-target-space-type.png)

#### Select the target region

Pick the CloudHub region to deploy the gateway to — for example,
**Cloudhub-US-East-2**.

![Select the target region quick-pick](images/50-select-target-region.png)

#### Confirm the gateway name

Confirm or edit the default gateway name, then press **Enter**.

![Enter a name for the gateway, showing the default name](images/51-gateway-default-name.png)

## 3. Wait for the gateway to deploy

Either path (Command Palette or manual) redirects to the gateway's
**Dashboard** in Runtime Manager, showing status **Starting...** while it
deploys. Wait until the status shows the gateway is running before continuing
— the dashboard also shows the gateway's public and cluster endpoints.

![Gateway Dashboard showing status Starting...](images/52-gateway-dashboard-deploying.png)

Once deployed, the status turns green and shows **Running**.

![Gateway Dashboard showing status Running](images/53-gateway-dashboard-running.png)

---

**Previous:** [Phase 4 — Set Up Mock Agents and MCP Servers](04-mock-agents-and-mcps.md) ·
**Next:** [Phase 6 — Build the Agent Network](06-build-agent-network.md)
