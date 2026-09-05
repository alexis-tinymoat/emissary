# Vision

Emissary is an AI agent that represents a person or business in the world —
**inbound and outbound**, and increasingly **agent-to-agent** rather than
only agent-to-human.

Outbound: it goes looking on your behalf — for opportunities, people,
information — and prepares what it finds for your review before anything
ever leaves in your name. Inbound: it's the first thing that meets what
comes at you — a request, an inquiry, an offer — and triages, drafts, or
answers, again with you as the approver for anything consequential. As more
of the other side of these interactions is itself an agent, not a human, the
representative's job shifts: less "write a nice email," more "state your
position, constraints, and facts precisely enough that another agent can act
on them correctly."

The commitment that survives every use case Emissary is put to: it earns the
right to act with increasing autonomy by first being trustworthy at lower
stakes — draft-ready, not send-ready, until a human decision says otherwise.

## Why this, why now

Two things made this buildable rather than aspirational:

- **The infrastructure already exists and is proven.** A LiteLLM gateway,
  Notion-as-database, scheduled background jobs independent of any live
  chat session, and a "verify against the real target before writing code"
  discipline — all already running in production for an unrelated content
  pipeline. Emissary reuses that, it doesn't invent new plumbing.
- **Agent-to-agent interaction is becoming a real channel**, not just a
  buzzword — job boards, marketplaces, and inboxes are increasingly read and
  sometimes populated by agents on the other side too. A representative
  built for that has to reason in structured facts and explicit constraints,
  not persuasive prose — closer to a negotiation protocol than a form letter.

## What ships first (MVP) vs. what this is for

The MVP is deliberately narrow: a single brand (Fast Forward Associates,
private), a single source (one freelance-mission job board), outbound only,
scan-and-score only — no drafting, no sending. It exists to prove the loop
end-to-end against real data before anything broader is attempted. It is a
**first tenant of the vision, not its definition** — the scoring logic,
source list, and "recruiting" framing in that MVP are specific to one
person's one use case, not the shape of what Emissary is.

Broadening from there means, roughly in order of how much new ground each
step covers:
1. More sources for the same use case (other job/mission boards).
2. Turning scan-and-score into actual outbound drafting — entity research,
   fact-constrained message drafting, and a critic/gate chain before
   anything reaches draft-ready — still never auto-sent.
3. Inbound representation — the harder, more valuable direction: fielding
   what comes in, not just seeking what to go after.
4. More than one principal — the same representative pattern applied to a
   different person or brand, proving the core isn't hard-wired to one
   business's specifics.

## What this repo is, right now

A placeholder. Nothing has shipped here yet — the private `fastforward-associates`
repo holds the real, running MVP. This repo exists so the *system's* identity
is separate from any one business that happens to run on it, and will hold
whatever of that system is genuinely generic enough to publish — a
Notion-as-database toolkit, a capped-spend LLM-key isolation pattern, an
agent-to-agent message schema — once there's something real to put here and
a clear line drawn around what stays private (scoring criteria, target
lists, and other business-specific logic never belong in a public repo).
