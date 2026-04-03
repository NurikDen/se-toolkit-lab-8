---
name: lms
description: Use LMS MCP tools for live course data
always: true
---

# LMS Skill

You have access to live LMS data through MCP tools. Use them to answer questions about courses, labs, learners, and analytics.

## Available tools

| Tool | What it does | When to use |
|------|-------------|-------------|
| `lms_health` | Checks if the LMS backend is healthy and reports item count | User asks about system health, backend status, or "is the LMS up?" |
| `lms_labs` | Lists all labs available in the LMS | User asks about labs without naming one, or you need to know what labs exist |
| `lms_learners` | Lists all learners registered in the LMS | User asks about who is enrolled or registered |
| `lms_pass_rates` | Gets pass rates (avg score and attempt count per task) for a lab | User asks about scores, pass rates, or how well learners are doing on tasks |
| `lms_timeline` | Gets submission timeline (date + submission count) for a lab | User asks about submission activity over time |
| `lms_groups` | Gets group performance (avg score + student count per group) for a lab | User asks about group performance or compares groups |
| `lms_top_learners` | Gets top learners by average score for a lab | User asks about top performers or leaderboards |
| `lms_completion_rate` | Gets completion rate (passed / total) for a lab | User asks about completion, how many finished, or pass/fail ratios |
| `lms_sync_pipeline` | Triggers the LMS sync pipeline | User asks to refresh or sync data, or when tools return stale/empty data |

## Strategy

- **If the user asks for scores, pass rates, completion, groups, timeline, or top learners without naming a lab:** call `lms_labs` first to see what labs are available.
- **If multiple labs are available:** use the shared `structured-ui` skill to present the choice on supported channels. On plain text channels, list the labs briefly and ask the user to pick one.
- **Use each lab title as the default user-facing label** unless the tool output gives a better identifier.
- **If the backend is healthy but returns no data:** suggest calling `lms_sync_pipeline` to refresh the data, then retry the original query.
- **Format numeric results nicely:** show percentages with one decimal (e.g., `75.3%`), counts as integers, and keep tables concise.
- **Keep responses concise.** Don't dump raw JSON — summarize the key numbers the user cares about.

## When the user asks "what can you do?"

Explain your current capabilities honestly:
- You can query live LMS data: available labs, learner lists, pass rates, completion rates, group performance, submission timelines, and top learners.
- You can check if the LMS backend is healthy.
- You can trigger the data sync pipeline.
- You do **not** have access to individual learner passwords, grades outside the LMS, or the ability to modify course content.

## Error handling

- If a tool call fails with a connection error, tell the user the LMS backend may be unreachable and suggest they check the service status.
- If a tool returns empty results for a lab that should have data, suggest running `lms_sync_pipeline` and retrying.
