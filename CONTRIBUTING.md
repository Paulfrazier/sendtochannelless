# Contributing a scenario

Got a good scenario for the quiz? Open a PR — it's a one-file change.

## TL;DR

1. Click here to edit `index.html` directly on GitHub: <https://github.com/Paulfrazier/sendtochannelless/edit/main/index.html>
2. Find the `SCENARIOS` array (search for `const SCENARIOS = [`).
3. Add your scenario object — copy the template below.
4. GitHub will fork the repo and open a PR. Done.

## Template — copy and fill this in

```js
{
  q: "What you're about to reply with, inside an existing thread. One sentence.",
  correct: "thread", // one of: "thread", "also", "new"
  why: {
    thread: "What you'd say if the user picks 'Reply in thread only'.",
    also: "What you'd say if the user picks 'Also send to #channel'.",
    new: "What you'd say if the user picks 'Start a new top-level message'."
  }
}
```

Paste it into `SCENARIOS` (anywhere is fine — the quiz shuffles each session).

## Style guidelines

- **Most correct answers should be `thread`.** That's the pedagogical point: people reach for "also send" thinking it's helpful, but it usually just doubles the noise and confuses the channel about where the conversation lives. Bias the bank that way.
- **`also` is for the narrow legit case** — the thread reached a real conclusion the channel needs to see (resolution of an incident the channel was watching, a final decision, an answer to a question everyone's been waiting on, scope-expansion where what started as a thread topic now affects everyone).
- **`new` is correct when the urge to also-send is actually a signal you have a new topic** — a poll, a rewrite proposal, an unrelated announcement, a topic that drifted partway through the thread, a retro that deserves its own thread.
- **Frame the `q` as a reply someone is about to type inside a thread.** It works best if the q quotes or paraphrases the actual reply.
- **Keep `q` short.** One sentence. Quote-style works well: `"In a thread, you reply: \"shipping the dashboard refactor next week.\""`
- **Keep `why` punchy.** One sentence each. Name the failure mode for the wrong answers (e.g. "Then every individual update gets blasted to the channel, defeating the point of the thread.").

## Examples to study

The `SCENARIOS` array already has 40 of them — see `index.html`. Look at any of them for tone and length.

## Don't worry about

- The order in the array — the quiz shuffles every session.
- Duplicates with other scenarios — the bank is meant to grow, and similar themes from different angles are fine.
- Formatting — your editor will run prettier on save, or just match the surrounding style.
