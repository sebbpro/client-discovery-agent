# CLAUDE.md — sebbpro-discovery

Plugin marketplace for the **Discovery phase**: skills a **client runs in their own Claude account**. One repo per engagement phase (`sebbpro-discovery`, later e.g. `sebbpro-pilot`) — a client gets read access only when that phase starts. Everything here is
readable by every client who gets access — write accordingly.

## Rules

1. **Client-safe only.** No scoring methods, price logic, proposal templates or other consulting IP —
   those stay in the private `sebbpro/sebbpro-skills` repo (`ai-discovery`). Skills here collect and
   structure; evaluation happens on the sebb.pro side.
2. **No client data in this repo**, ever. Not even as examples.
3. **Operator is `sebb.pro`**, never a personal name. No internal vocabulary in client-facing text
   (no "Core", "Runde", "Operator", "Scoring").
4. **Never ask the client to grade the skill.** Offer, don't solicit (see the ai-business-os rule).
5. Wording lives in `assets/` per language; the procedure in `SKILL.md`.
6. Changes via PR; bump `version` in `plugins/sebbpro-discovery/.claude-plugin/plugin.json`
   (minor = new skill, patch = fix). Summary format changes also bump the `format` version in
   `ai-discovery-intake/assets/zusammenfassung.de.md`, because `ai-discovery` reads it.
