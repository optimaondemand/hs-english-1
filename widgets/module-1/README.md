# Module 1 Widget — The Theatre of Dionysus (Grammar & Vocabulary)

A single, polished, theatre-themed game covering Module 1 grammar (subordinate clauses, appositives, parallel structure, rhetorical questions) and vocabulary (justice, duty, polis, piety, hubris, anagnorisis, dramatic irony…). Navy/cyan chrome with the ELA accents **gold + plum**; the muted crimson is used **only** as functional "incorrect" feedback (no green, no red decoration). Keyboard-accessible, touch-friendly, reduced-motion aware, with an IEP/504 extended-time toggle.

**One file, two behaviors.** `index.html` auto-detects its environment:

## 1. Graded biweekly quiz → SCORM 1.2 (posts to the Canvas gradebook)
When the page is running inside a SCORM 1.2 player, it reports a **score (0–100)** and **lesson status** (`passed` at ≥70, else `completed`) to the gradebook, then locks (no replay). Mastery score is 70.

**To deploy as the graded biweekly quiz (weeks 2, 4, …):**
1. Zip the **contents** of this folder (`index.html` + `imsmanifest.xml`) at the root of the zip — not the folder itself.
2. In Canvas: **Settings → Import Course Content → SCORM package**, upload the zip, and choose to add it as a **graded assignment**.
3. Set the point value; Canvas maps the SCORM score (0–100) to the assignment.

> Swap the biweekly content by editing the `QUESTIONS` array at the top of the `<script>` in `index.html` (each item: `q`, four `a` options, `c` = index of the correct one). Re-zip to redeploy.

## 2. Off-week practice → plain iframe (ungraded, unlimited tries)
When embedded as a normal web page (no SCORM player), it runs in **practice mode**: unlimited replays, nothing recorded. Host on the course GitHub Pages widget repo and embed in an in-lesson page:

```html
<iframe src="https://<org>.github.io/<repo>/module-1/index.html"
        style="width:100%;height:720px;border:0;" title="Grammar & Vocabulary practice"></iframe>
```

## Theming the game per module
This is the Module 1 skin (Greek masks / theatre). Later modules reuse the same engine with a new backdrop and `QUESTIONS` set per the audit's per-module theme table (Arthurian for M2, pilgrimage for M3, Renaissance for M4, etc.), keeping the gold/plum palette.

## Notes
- Content is original (grammar rules + individual vocabulary words are not copyrightable); no literary text is reproduced.
- The SCORM API discovery walks parent/opener frames per the SCORM 1.2 convention; if no API is found it silently falls back to practice mode, so the same file is safe to embed anywhere.
