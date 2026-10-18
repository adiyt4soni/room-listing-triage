---
name: room-listing-triage
description: Find, verify, rank and shortlist rooms or flats to rent from listing sites - hard filters, a finder pass that logs every listing seen, a skeptic pass that checks each survivor on its live page, scam rules, photo review by agents, a scored visual shortlist, and drafted messages that are sent only with the user's approval. Use when the user is looking for a room, flat share or short let and wants listings found, checked or compared.
---

# Room and listing triage

Narrows hundreds of listings across platforms to a short, verified list. The method is generic; the filters and
anchors are the user's.

## 0. Absolute rules
1. **Never pay, book, reserve or accept terms.** Booking is always the user's action.
2. **Never send a message without the user's approval in that session.** Approval does not carry over.
3. **Never create accounts or type passwords.** CAPTCHAs, phone checks and ID checks go to the user.
4. **Scam rules are hard rules.** Drop the listing, or stop and report, if:
   - money (deposit, holding fee or rent) is asked for before the user has seen the room in person;
   - a fee goes to someone abroad, or who "can't show the room";
   - passport or ID copies are asked for before a viewing;
   - the price is far below comparable rooms in the area (flag anything under about 70% of the area median);
   - the host pushes off-platform before any viewing, combined with any of the above.
5. **Never misrepresent the user.** Profile and message wording comes from the user's own blurb. No personal
   identifiers or private history in any profile or message.
6. **Ethnicity is never a filter.** Areas are judged on crime data and commute; households on lifestyle and
   compatibility, as the user describes them.
7. **If anything unexpected happens, stop and report** (login wall, block, CAPTCHA, changed layout).
8. **A listing whose live page could not be checked is a LEAD**, labelled as one.

## 1. Parameters (ask the user, write them down)
Rent band and what counts (bills, platform fees), move-in window, minimum and maximum term, commute anchors and the
door-to-door limit at a weekday arrival time, room must-haves (bed size, desk fits, private bathroom), furnished,
wifi, washing machine, household size, diet or smoking rules, areas to avoid (see `uk-area-safety-screen`), and the
ranking order.

## 2. Pre-flight
Confirm today's date and the parameters. Check the user is logged in to each platform in their own browser; if not,
stop and ask. Make sure the area avoid list is approved.

## 3. Finder pass
Search each platform with its own filters set as close to the parameters as it allows. Write **one row per listing
seen** to `listings/listings-YYYY-MM-DD.tsv` (platform, URL, title, price, bills, area, postcode district, room type,
bathroom, household size, ages if stated, minimum term, available date, status). Dropped listings keep their row
with a reason code. Report the raw count per platform as the positive control.

## 4. Skeptic pass (live page, every survivor)
Open each surviving listing's live page and verify price, dates, bathroom, furnishing, washing machine, wifi,
flatmates and ages, smoking rules and minimum term. Get the commute from the official journey planner for the
postcode district (approximate; say so). Check every scam rule. Anything not fully checked is a LEAD.

## 5. Photo review
Reviewer agents on a strong model judge the photos with a fixed checklist: photo kinds, bed size, room size, whether
a desk and chair fit, natural light, modern / newer / dated, bathroom private or shared and its condition, red flags,
a room score 1-10, the best bedroom and bathroom photos, a one-line description, and who you'd live with. Save the
results as JSON per batch.

## 6. Score and rank
Apply the user's ranking order and show a **score breakdown** per listing so the user can see why it ranks where it
does. Keep the top 20-30, then an "ask the host" section (good rooms with a term or detail to confirm), then an
appendix of near-misses with the reason each dropped.

## 7. Present
Build a visual page: photos (bedroom first, then bathroom), price (rent / bills / fee-inclusive total), area,
commute to each anchor, bathroom, room-size verdict, flatmates, minimum term, the score breakdown, the link, and a
pick / skip / maybe control that saves the user's choices so they can be read back. Also save the batch as
`listings/shortlist-YYYY-MM-DD.md`.

## 8. Draft messages for the picks
One per listing: short and friendly, from the user's blurb; asks for a viewing with 2-3 concrete slots; asks the
open questions (term, bills, flatmates). Save to `messages/YYYY-MM-DD.md`. **Show the batch; send only what the user
approves in that session.**

## 9. Track and log
Track every contacted listing (drafted / sent / replied / viewing booked / viewed / offered / declined), dated,
newest first. Add a dated entry to the project's `memory.md`.
