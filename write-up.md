# Write-Up: Daily Reflection Tree - Design Rationale

**Candidate Assignment: DT Fellowship - Daily Reflection Tree**
**Part A: Design Rationale **

---

## Why These Questions

The hardest part of this assignment wasn't choosing questions - it was choosing questions that don't feel like a quiz.

A reflection tool fails the moment an employee can see what the "right answer" is and click toward it. So every question was designed around a principle: **the options must feel equally valid in the moment**, even when they point in opposite directions psychologically. A person who feels like a victim today should be able to pick their answer without feeling accused.

**Axis 1 (Locus of Control):** The opening question - *"If today were a headline, what would it say about you?"* - is deliberately personal and narrative. It activates self-authorship before the branching even begins. Options like "Today happened to me more than I happened to it" are phrased sympathetically, not as failures. This matters because Rotter's original research found that locus of control is situational - the same person can feel internal on a good week and external after a string of setbacks. The tree honors this by not treating external locus as a character flaw, only as a current position.

**Axis 2 (Contribution vs Entitlement):** Campbell et al.'s research on psychological entitlement is clear: entitled individuals genuinely don't perceive themselves as entitled. They believe they've earned the recognition they're seeking. So the entitlement-facing questions had to be phrased with enough plausibility that an entitled person wouldn't filter them out. *"Did you feel you deserved more recognition than you got?"* reads as an honest feeling, not an accusation - because it is one. The branching then asks a follow-up that invites reflection without shame: *"Is there something you could have offered that you held back?"*

**Axis 3 (Radius of Concern):** Maslow's 1969 paper on self-transcendence (and Batson's 2011 work on perspective-taking) both point to the same insight: expanding one's frame of concern is not altruism, it's cognitive. The questions in Axis 3 start with the question *"Who shows up in the story?"* because Maslow's transcendence isn't about grand sacrifice - it's about whose reality you hold in mind. The options deliberately move from self -> specific others -> team -> beyond team, letting the employee locate themselves honestly on that spectrum.

---

## How the Branching Was Designed

The tree uses a **two-stage branching pattern** in each axis:

1. **Stage 1 - Broad orientation question:** Determines whether the employee is currently leaning toward the growth pole or the challenged pole of that axis. This is kept implicit - the employee doesn't know they're being routed.

2. **Stage 2 - Nuanced follow-up:** Deepens the inquiry. For employees already at the growth pole, the follow-up asks for specificity (can you name a concrete moment?). For employees at the challenged pole, the follow-up opens a door toward awareness without forcing them through it.

**Key trade-off:** I chose to keep the tree relatively shallow (2-3 questions per axis) rather than deeply recursive. The reasoning: a 25-30 node tree that flows in 5-7 minutes is actually used; a comprehensive 80-node tree that takes 20 minutes is abandoned by week two. Depth was sacrificed for sustainability.

**Cross-axis connection:** The bridge nodes are not just transitions - they're designed to linguistically carry the previous axis's insight forward. Bridge 1->2 says *"now let's shift from how you handled things - to what you gave"*, which frames contribution as an active choice (echoing Axis 1's agency). Bridge 2->3 says *"let's zoom out from what you gave to who you were thinking about"*, which naturally extends contribution outward (deepening Axis 3's radius concept).

---

## Psychological Sources

| Source | How it influenced the tree |
|---|---|
| Rotter, J.B. (1966). *Generalized expectancies for internal vs. external control of reinforcement.* | Framing of Axis 1 questions: options map to internal/external without labelling them |
| Dweck, C. (2006). *Mindset: The New Psychology of Success.* | Growth mindset framing of reflection nodes - awareness after the fact is itself growth |
| Campbell, W.K. et al. (2004). *Psychological entitlement: Interpersonal consequences and validation of a self-report measure.* | Design of Axis 2 entitlement questions - sympathy without invisibility |
| Organ, D.W. (1988). *Organizational Citizenship Behavior.* | Contribution axis framing - discretionary effort that goes beyond formal requirements |
| Maslow, A.H. (1969). *The farther reaches of human nature.* | Axis 3 design - transcendence is not abstraction; it's knowing who you're working for |
| Batson, C.D. (2011). *Altruism in Humans.* | Perspective-taking as a cognitive act, not a feeling - informs the "who shows up in the story" question |

---

## What I'd Improve With More Time

1. **Longitudinal state.** Right now the tree has no memory of yesterday. A real deployment would show the employee their Axis 1/2/3 positions over time - surfacing if they've been running on external locus for three weeks, or if their contribution radius has been widening. Patterns are more actionable than single sessions.

2. **More Axis 3 depth.** The Radius axis currently has fewer branching paths than Axis 1. Self-transcendence is psychologically the most complex of the three - it deserves 3-4 questions exploring not just *who* the employee thought about, but *how* thinking about others changed their decisions. This was trimmed for session length.

3. **Persona testing.** I'd run five distinct employee personas through the tree (the burned-out individual contributor, the ambitious junior, the resentful senior, the genuinely altruistic team lead, the checked-out quiet-quitter) and trace their paths. I suspect Axis 2 needs sharper option language for the quiet-quitter persona - they would likely click "I gave what I had" when the more honest answer is "I gave what was safe."

4. **Reflection language calibration.** The reflection nodes currently lean slightly toward affirmation. A wiser colleague doesn't always affirm - sometimes they say *"hmm"* and leave the silence. The tree could use a version of this: a reflection node that simply names what was surfaced, without editorializing.

---

*Total node count: 40 nodes | Questions: 12 | Decision nodes: 10 | Reflection nodes: 8 | Bridge nodes: 2 | Summary: 1 | Start/End: 2*
