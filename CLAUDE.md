# CLAUDE.md — sebbpro-ai

Plugin marketplace for skills a **client runs in their own Claude account**. **One marketplace (this repo), one plugin per engagement phase** (`plugins/discovery`, `plugins/pilot`, …), one or more skills per plugin. This repo is **public**: everything here is readable by anyone — write accordingly.

The client sees `plugin:skill` in the chat (e.g. `discovery:intake`), never the repo name — keep plugin and skill names short and free of internal vocabulary.

## Rules

1. **Client-safe only.** No scoring methods, price logic, proposal templates or other consulting IP —
   those are not part of this repo. Skills here collect and structure; evaluation happens on the
   sebb.pro side.
2. **No client data in this repo**, ever. Not even as examples.
3. **Operator is `sebb.pro`**, never a personal name. No internal vocabulary in client-facing text
   (no "Core", "Runde", "Operator", "Scoring").
4. **Never ask the client to grade the skill.** Offer, don't solicit.
5. Wording lives in `assets/` per language; the procedure in `SKILL.md`.
6. Changes via PR; bump `version` in the changed plugin's `.claude-plugin/plugin.json`
   (minor = new skill, patch = fix). A new phase = new `plugins/<phase>/` plus an entry in
   `.claude-plugin/marketplace.json` and the README table.
7. Output formats (`format:` in the summary front matter) are contracts with the sebb.pro-side
   evaluation: changing one bumps its version, e.g. `ai-discovery-intake/1` in
   `plugins/discovery/skills/intake/assets/zusammenfassung.de.md`. The identifier
   `ai-discovery-intake/1` is kept stable on purpose even though the skill is now `intake`.
