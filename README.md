# Daily Reflection Tree
### DT Fellowship Assignment — Data Analytics Internship

A deterministic end-of-day reflection tool built as a structured decision tree. The tool walks employees through three psychological axes — **Locus of Control**, **Contribution Orientation**, and **Radius of Concern** — using a fully deterministic branching system. No LLM is called at runtime.

---

## Repository Structure

```
/tree/
  reflection-tree.json      ← Part A: Full tree data (40 nodes)
  tree-diagram.md           ← Part A: Mermaid visual diagram

/agent/
  index.html                ← Part B: Runnable web agent (single file, no dependencies)

/transcripts/
  persona-1-transcript.md   ← External/Entitled/Self-centric path
  persona-2-transcript.md   ← Internal/Contributing/Altrocentric path

write-up.md                 ← Part A: Design rationale (2 pages)
README.md                   ← This file
```

---

## Part A: Reading the Tree

**File:** `/tree/reflection-tree.json`

The tree is a JSON array of node objects. Each node has:

| Field | Description |
|---|---|
| `id` | Unique node identifier |
| `type` | Node type: `start`, `question`, `decision`, `reflection`, `bridge`, `summary`, `end` |
| `text` | What the employee sees. `{NODE_ID}` placeholders interpolate earlier answers. |
| `options` | Array of fixed choice strings (question nodes only) |
| `routes` | Array of routing rules (decision nodes only): `{match: [...answers], target: "NODE_ID"}` |
| `target` | Direct next node (for non-decision, non-question nodes) |
| `signal` | State tally: e.g. `"axis1:internal"` increments the internal locus counter |

**To trace a path manually:**
1. Start at node `START`
2. For `start`, `reflection`, `bridge`, `end` nodes → follow `target`
3. For `question` nodes → the employee picks an option; check `DECISION_TRIGGER` map in the agent to find which decision node evaluates this question's answer
4. For `decision` nodes → match the previous answer against each route's `match` array → follow the matching `target`
5. For `summary` → tally signals per axis, dominant pole = the one with higher count

**Visual diagram:** Open `/tree/tree-diagram.md` in any Mermaid-compatible renderer (GitHub, mermaid.live, VS Code + Mermaid extension).

---

## Part B: Running the Agent

**No installation required.** The agent is a single self-contained HTML file.

```bash
# Option 1: Open directly in browser
open agent/index.html

# Option 2: Serve locally (avoids any browser restrictions)
cd agent
python3 -m http.server 8080
# Then visit http://localhost:8080
```

**How it works:**
- The entire tree is embedded as a JavaScript object (mirroring the JSON structure)
- State is tracked in a plain JS object: `{ answers, signals, stepCount }`
- All branching is pure lookup — no LLM, no randomness, no external API calls
- Given identical answers, the path is always identical
- Works fully offline

---

## Node Count

| Type | Count |
|---|---|
| start | 1 |
| question | 12 |
| decision | 10 |
| reflection | 8 |
| bridge | 2 |
| summary | 1 |
| end | 1 |
| **Total** | **40** |

---

## The Three Axes

| Axis | Spectrum | Key Psychology |
|---|---|---|
| 1. Locus | Victim ↔ Victor | Rotter (1966) Locus of Control; Dweck (2006) Growth Mindset |
| 2. Orientation | Entitlement ↔ Contribution | Campbell et al. (2004); Organ (1988) OCB |
| 3. Radius | Self-centric ↔ Altrocentric | Maslow (1969) Self-Transcendence; Batson (2011) Perspective-Taking |

---

## Design Principles

1. **No moralizing.** Every path ends with self-awareness, not judgment.
2. **Fixed options only.** No free text. Options are designed so all feel equally plausible.
3. **Interpolation, not generation.** Reflection text uses `{NODE_ID}` to reference earlier answers — no LLM required.
4. **Three axes, one conversation.** Bridges explicitly carry the previous axis's insight into the next.
5. **Deterministic.** Same answers → same path → same reflection. Always.

---

*Built for DeepThought Fellowship Assignment | April 2026*
