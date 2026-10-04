# Plan to Win — Meta VR Start Developer Competition 2026

## Honest assessment first

Chris has no XR background, no Quest device, and isn't enrolled in the VR Start program (enrollment is blocked on his Meta developer sign-in). This competition rewards exactly the things he hasn't done: hand-tracking interaction design, spatial UX, and Quest performance engineering at 60fps. The field will include working XR studios.

**That does not make it unwinnable — but it makes it the highest-risk of the three campaigns, and it should not start until the three gates below are cleared.** If the gates don't clear by ~Oct 12, park this repo and put the energy into PayPal + Graph Hacks.

## GO / NO-GO gates
- **Gate 1 — Enrollment (Chris, ~30 min):** Meta developer sign-in → join the VR Start Program → confirm membership. Without this, no submission is possible. Currently blocked, awaiting Chris.
- **Gate 2 — Hardware (Chris, ~$300):** acquire a Quest 3S for on-device testing. Judges test on device; hand-tracking UX cannot be iterated in a simulator. No device → no credible entry.
- **Gate 3 — Time box (Chris):** 3–4 focused weeks to learn hand-first interaction patterns. This is a new medium, not a new framework.

## Concept (if GO): Briefing — a hands-first AI chief of staff

**Productivity track, New Experience division.** A seated, passthrough morning ritual: your day floats around you as grabbable cards — calendar, tasks, priorities. You talk to an AI chief of staff (voice-first, Chris's IVR/voice background is the edge here) that briefs you, reorders the day as plans change, and parks decisions. Hands move cards; voice directs the agent; the real room stays visible in passthrough so it works at a desk or on a couch. One satisfying session: under 10 minutes, start to done.

Why this concept and not a game: games compete against studios with art teams. A productivity utility competes on interaction design and usefulness — closer to Chris's strengths — and the **AI Innovation ($25k)** and **10-Minute Challenge ($20k)** side prizes are realistic targets even without a track podium.

## Why it could win — mapped to the actual criteria

| Criterion (25% each) | How Briefing scores |
|---|---|
| **Innovation & Creativity** | Voice-directed agentic productivity in passthrough is still rare; most Quest productivity apps are floating 2D panels. An AI that reorganizes your spatial workspace by conversation is a genuine interaction-model bet. |
| **Experience Design** | Seated, 10-minute ritual; clear onboarding ("here's your day — grab what matters"); habit-forming by construction (it's a morning routine). Passthrough is purposeful: the room is the office, cards anchor to real surfaces. |
| **Technical Implementation** | Hand tracking + gaze + voice as the full input stack; spatial anchors for card persistence; 60fps budget treated as a design constraint from day one (low-poly, baked lighting, no physics sims). |
| **Polish & Presentation** | Real on-device footage, calm art direction, clean sound. The video is one continuous morning session — no AI-generated filler, per the rules' explicit warning. |

## Tech approach
- **IWSDK / WebXR**, hosted link (Vercel) — avoids the native APK build chain and Dashboard release-channel process; fastest path for a web-strong builder
- Hand tracking + eye/gaze via Meta's Interaction SDK; Web Speech API (or equivalent) for voice with a hand-only fallback
- LLM agent backend for the chief-of-staff dialogue and day-planning logic
- Performance: aggressive polygon/texture budgets, no per-frame allocations, test on-device from week one

## Differentiation vs typical entries
Most entries will be games from XR-native teams, or ports adding hand support as a checkbox. A voice-first agentic productivity app built hands-first from zero is a differentiated lane with thinner competition — and it aims at side prizes ($25k AI Innovation, $20k 10-Minute Challenge) where a polished small entry can beat an ambitious buggy one.

## Milestones (only if gates clear; working back from Nov 18, 8:00 PM UTC)
- **Oct 5–11 — Gates + spike:** enrollment confirmed, Quest 3S in hand, IWSDK hello-world with hand tracking running on device; kill the project here if hand-tracking iteration feels intractable
- **Oct 12–26 — Core interaction:** grabbable cards, gaze+pinch selection, voice command loop, passthrough room layout; one end-to-end "morning brief" session working on device
- **Oct 27–Nov 8 — Agent + polish:** chief-of-staff dialogue, day re-planning, spatial anchors; art/sound pass; 60fps perf budget enforced
- **Nov 9–15 — Submission package:** <3 min video of REAL on-device gameplay; Devpost writeup (inspiration, build, future plans)
- **Nov 16–18 — Buffer:** Chris reviews on-device, approves, submits. No changes after deadline — the entry is frozen as submitted.

## Biggest risks
1. **The medium is new to the builder.** Hand-tracking UX has brutal learnability cliffs (pinch reliability, hand fatigue, FoV limits). Mitigation: ruthless scope control — cards + voice + one ritual, nothing else.
2. **60fps on Quest via WebXR.** Browser-based XR pays a performance tax. Mitigation: treat the frame budget as the primary design constraint; profile on-device weekly from the start.
3. **"Not a wrapper" rule.** An AI chatbot floating in space fails the originality test. Mitigation: the spatial interaction model (grabbable day-cards, anchored room layout, voice-directed agent) must be entrant-built and central — the LLM is a component, not the product.
4. **Time.** Three gates plus a new medium in six weeks alongside two other hackathons. Mitigation: the Oct 11 spike is a hard kill-point. If it's not clicking, walk away with no sunk-cost guilt.
