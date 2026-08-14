# Phase 6 — Build the Agent Network

With the Agent Network Gateways up and running, build the first example
agent network.

## Contents

- [1. Create the Agent Network project](#1-create-the-agent-network-project)

## 1. Create the Agent Network project

With the gateway running, create the agent network project in Anypoint Code
Builder. Open the Command Palette (**Cmd+Shift+P**) and run **"MuleSoft:
Create an Agent Network Project..."**, or use the Welcome view's **Create →
Create an Agent Network** link.

![Command Palette running MuleSoft: Create an Agent Network Project, with the Create an Agent Network link in the Welcome view](images/54-create-agent-network-project-command.png)

In the **Create an Agent Network Project** dialog, enter a **Project Name**
(e.g. `IT Help Investigation Agent Network`), confirm the **Project Location**,
pick the **Business Group** (e.g. **Salesforce**), and click **Create
Project**.

![Create an Agent Network Project dialog, with project name, location, and business group filled in](images/55-create-agent-network-project-dialog.png)

You land in the scaffolded project. The Explorer shows `brokers/broker1.agent`,
`agent-network.yaml`, and `exchange.json`. `agent-network.yaml` defines the
network — `agentNetwork: 2.0.0`, the network's `label`, and a
`registry.agents` example agent (`myAgent`, platform `Bedrock`, an `a2a` card).
The **Canvas** view visualizes the broker's flow: a Generator, an Executor
(`RunAction`), a Router (`ResultRouter`) with **Success**/**Otherwise**
branches, and Echo nodes for the success and error responses.

![Scaffolded agent network project, showing agent-network.yaml and the Canvas view](images/56-scaffolded-agent-network-project.png)

---

**Previous:** [Phase 5 — Set Up Agent Network Gateways](05-set-up-agent-network-gateways.md)
