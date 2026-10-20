# AgentAwake for Claude Code

AgentAwake already sees when Claude Code is working (Claude runs `caffeinate` while it writes a reply). This plugin gives Claude, at the start of each session, the rule for keeping the Mac awake during work that continues after a reply ends: background jobs, `/loop` waits and background agents.

Needs [AgentAwake](https://syncedge.tech/en/agentawake/) installed in `/Applications`. Without it the hooks do nothing.

## Install

In Claude Code:

```
/plugin marketplace add SyncEdge/agentawake-releases
/plugin install agentawake@syncedge
```

On Claude Code 2.1.275 or later, one step does both:

```
/plugin install agentawake --marketplace SyncEdge/agentawake-releases
```

The same hooks can be added without this plugin from AgentAwake's **Connect agents…** window.

## What it runs

One `SessionStart` hook: `/Applications/AgentAwake.app/Contents/Helpers/agentawake rules`, which prints a short instruction for Claude. If the app isn't there, the hook prints nothing and exits successfully. The plugin collects, stores and sends no data.
