# Lab 8 — Report

Paste your checkpoint evidence below. Add screenshots as image files in the repo and reference them with `![description](path)`.

## Task 1A — Bare agent

**Command:** `cd nanobot && uv run nanobot agent --logs --session cli:task1a-loop -c ./config.json -m "What is the agentic loop?"`

<!-- Run this on your VM where services are running and paste the agent's response below -->
> [Paste agent response here after running on VM]

**Command:** `cd nanobot && uv run nanobot agent --logs --session cli:task1a-labs -c ./config.json -m "What labs are available in our LMS?"`

<!-- Run this on your VM where services are running and paste the agent's response below -->
> [Paste agent response here after running on VM — should NOT return real backend data at this stage]

## Task 1B — Agent with LMS tools

**Command:** `cd nanobot && uv run nanobot agent --logs --session cli:task1b-labs -c ./config.json -m "What labs are available?"`

<!-- Run this on your VM and paste the agent's response below — should return real lab names -->
> [Paste agent response here after running on VM]

**Command:** `cd nanobot && uv run nanobot agent --logs --session cli:task1b-health -c ./config.json -m "Is the LMS backend healthy?"`

<!-- Run this on your VM and paste the agent's response below -->
> [Paste agent response here after running on VM]

## Task 1C — Skill prompt

**Command:** `cd nanobot && uv run nanobot agent --logs --session cli:task1c -c ./config.json -m "Show me the scores"`

<!-- Run this on your VM and paste the agent's response below — should ask which lab or list available labs -->
> [Paste agent response here after running on VM]

## Task 2A — Deployed agent

<!-- Paste a short nanobot startup log excerpt showing the gateway started inside Docker -->

## Task 2B — Web client

<!-- Screenshot of a conversation with the agent in the Flutter web app -->

## Task 3A — Structured logging

<!-- Paste happy-path and error-path log excerpts, VictoriaLogs query screenshot -->

## Task 3B — Traces

<!-- Screenshots: healthy trace span hierarchy, error trace -->

## Task 3C — Observability MCP tools

<!-- Paste agent responses to "any errors in the last hour?" under normal and failure conditions -->

## Task 4A — Multi-step investigation

<!-- Paste the agent's response to "What went wrong?" showing chained log + trace investigation -->

## Task 4B — Proactive health check

<!-- Screenshot or transcript of the proactive health report that appears in the Flutter chat -->

## Task 4C — Bug fix and recovery

<!-- 1. Root cause identified
     2. Code fix (diff or description)
     3. Post-fix response to "What went wrong?" showing the real underlying failure
     4. Healthy follow-up report or transcript after recovery -->
