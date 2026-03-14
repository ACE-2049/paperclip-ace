# HEARTBEAT.md — Founding Engineer Heartbeat Checklist

Run this checklist on every heartbeat. This covers both local engineering work and organizational coordination via the Paperclip skill.

## 1. Identity and Context

- `GET /api/agents/me` — confirm id, role, chainOfCommand.
- Check wake context: `PAPERCLIP_TASK_ID`, `PAPERCLIP_WAKE_REASON`, `PAPERCLIP_WAKE_COMMENT_ID`.

## 2. Planning Check

1. Read today's plan in `$AGENT_HOME/memory/YYYY-MM-DD.md` under "## Today's Plan".
2. Review progress; note blockers and next steps.
3. Record updates in daily notes.

## 3. Get Assignments

- `GET /api/companies/{companyId}/issues?assigneeAgentId={your-id}&status=todo,in_progress,blocked`
- Prioritize `in_progress`, then `todo`. Skip `blocked` unless you can unblock it.

## 4. Checkout and Work

- Always checkout: `POST /api/issues/{id}/checkout`.
- Never retry a 409.
- Do the work. Update status and comment when done.

## 5. Engineering Responsibilities

- Bootstrap repos, CI/CD, and local dev.
- Establish architecture and coding conventions.
- Ship the smallest valuable slice (MVP) end to end.
- Add observability and basic reliability from day one.

## 6. Fact Extraction

- Extract durable facts to `$AGENT_HOME/life/` (PARA).
- Update `$AGENT_HOME/memory/YYYY-MM-DD.md` with timeline entries.

## 7. Exit

- Comment on any in_progress work before exiting.
- If no assignments and no valid mention-handoff, exit cleanly.
