# Day Runner

One long-running Claude thread (the cloud session titled **Day Runner**) that runs Ben's working day: a morning brief, check-ins through the day, and a wrap-up that sets the next day's Top 3.

## How it works

| Piece | Where it lives |
|---|---|
| Thread | The cloud Claude Code session titled "Day Runner". Two scheduled tasks post into it. |
| Morning brief + check-ins | Scheduled task **Day Runner tick**: weekdays at 4:50, 7:50, 9:50, 11:50, 1:50 and 3:50 (Pacific) |
| Wrap-up | Scheduled task **Day Runner wrap-up**: weekdays at 8:25pm |
| Top 3 | Asana **My Tasks → MIP** section, hard-capped at 3 |
| Inbox | Asana **My Tasks → Unprocessed** (new assignments land there automatically) |
| Tasks Claude creates | Unprocessed, name prefixed `[Claude]` |

The full instructions the thread follows are in [PROMPT.md](PROMPT.md).

The scheduled tasks post into this one existing session rather than starting a new session each day, because sessions a schedule starts fresh don't get connectors (Asana, Gmail, Calendar, Slack, Grain) in this org.

## Daily rhythm

- **4:50am:** overnight sweep (Gmail, Slack, Calendar, Asana, Grain), then the morning brief: Top 3, today's calendar, up to 5 "needs you" items.
- **7:50am–3:50pm:** reports only what's new since the last check-in. Says "Nothing new" if nothing is. Sends a push notification only when something can't wait.
- **8:25pm:** wrap-up. Reviews today's Top 3, turns anything posted in the thread into tasks, and proposes tomorrow's Top 3. Ben confirms or swaps, then Claude moves the picks into MIP. Friday's wrap-up picks Monday's.

## Using the thread

- **Quick work** (about 10 minutes or less) happens in the thread.
- **Bigger work:** the thread starts a separate session for it and posts the link.
- **Scratchpad:** post notes, links and photos of your legal pad any time. They're captured into Asana at the wrap-up.

## Changing it

Edit [PROMPT.md](PROMPT.md); the scheduled tasks read it on every run. To change the times, ask Claude to update the two scheduled tasks.

This repo is public: keep anything personal (journal entries, client details) out of it.
