# Day Runner

A Claude thread that runs Ben's working day. Each weekday it opens one new session, posts a morning brief, checks in through the day, and closes with a wrap-up that sets the next day's Top 3.

## How it works

| Piece | Where it lives |
|---|---|
| Daily thread | A cloud Claude Code session started by the **Day Runner** scheduled task (Mon–Fri, 4:50am Pacific) |
| Check-ins | The 4:50am session schedules its own 8am, 10am, 12pm, 2pm and 4pm check-ins and an 8:30pm wrap-up (`send_later`) |
| Top 3 | Asana **My Tasks → MIP** section, hard-capped at 3 |
| Inbox | Asana **My Tasks → Unprocessed** (new assignments land there automatically) |
| Tasks Claude creates | Unprocessed, name prefixed `[Claude]` |

The full instructions the session runs on are in [PROMPT.md](PROMPT.md).

## Daily rhythm

- **4:50am:** overnight sweep (Gmail, Slack, Calendar, Asana, Grain), then the morning brief: Top 3, today's calendar, up to 5 "needs you" items.
- **8am–4pm:** reports only what's new since the last check-in. Says "Nothing new" if nothing is. Sends a push notification only when something can't wait.
- **8:30pm:** wrap-up. Reviews today's Top 3, turns anything posted in the thread into tasks, and proposes tomorrow's Top 3. Ben confirms or swaps, then Claude moves the picks into MIP. Friday's wrap-up picks Monday's.

## Using the thread

- **Quick work** (about 10 minutes or less) happens in the thread.
- **Bigger work:** the thread starts a separate session for it and posts the link.
- **Scratchpad:** post notes, links and photos of your legal pad any time. They're captured into Asana at the wrap-up.

## Changing it

Edit [PROMPT.md](PROMPT.md), then ask Claude to update the "Day Runner" scheduled task's prompt to match. The task keeps its run history when its prompt changes.

This repo is public: keep anything personal (journal entries, client details) out of it.
