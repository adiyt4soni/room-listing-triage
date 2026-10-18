# Room and listing triage

Finds, verifies, ranks and shortlists rooms or flats to rent, with scam rules and photo review, and drafts messages that are only sent with approval.

**Type:** Claude Code skill · **Area:** General skills

## What it does

- A finder pass logs one row for every listing seen on each platform, including the dropped ones with a reason.
- A skeptic pass opens each survivor's live page and checks price, dates, bathroom, furnishing, flatmates, term and commute; anything unchecked stays a LEAD.
- Reviewer agents judge the photos against a fixed checklist (bed size, desk fit, light, modern or dated, bathroom, red flags, a 1-10 score).
- Builds a scored visual shortlist with pick / skip / maybe controls, then drafts one short message per pick for the user to approve.

## Guardrails

- Never pays, books, reserves, signs up or sends without approval in the session.
- Hard scam rules: no money before an in-person viewing, no ID before a viewing, flag prices far below the area median.
- Ethnicity is never a filter.

## When it triggers

> Find, verify, rank and shortlist rooms or flats to rent from listing sites - hard filters, a finder pass that logs every listing seen, a skeptic pass that checks each survivor on its live page, scam rules, photo review by agents, a scored visual shortlist, and drafted messages that are sent only with the user's approval. Use when the user is looking for a room, flat share or short let and wants listings found, checked or compared.

## What's in this repo

- `SKILL.md`: the skill itself, the file Claude or Codex reads.
- Not included: No scripts are included.
- Written to be generic: where the skill relies on the user's own files, it names them by role, not by content.

## Install

```bash
mkdir -p ~/.claude/skills/room-listing-triage
curl -fsSL https://raw.githubusercontent.com/adiyt4soni/room-listing-triage/main/SKILL.md -o ~/.claude/skills/room-listing-triage/SKILL.md
```
