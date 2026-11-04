# CLAUDE.md — sebbpro-ai

Plugin marketplace for skills a **client runs in their own Claude account**. **One marketplace (this repo), one plugin per engagement phase** (`plugins/sebbpro-discovery`, …), one or more skills per plugin. This repo is **public**: everything here is readable by anyone — write accordingly.

The client sees `plugin:skill` in the chat (e.g. `sebbpro-discovery:intake`), never the repo name. Follow the naming convention below.

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
   `plugins/sebbpro-discovery/skills/intake/assets/zusammenfassung.de.md`. The identifier
   `ai-discovery-intake/1` is kept stable on purpose even though the skill is now `intake`.

## Naming convention

What a client sees in the chat is `<plugin>:<skill>`, e.g. `sebbpro-discovery:intake`.

| Level | Rule | Example |
|---|---|---|
| Repo | `sebbpro-<topic>`; this repo is the public client marketplace | `sebbpro-ai` |
| Marketplace (`name` in `marketplace.json`) | `<repo>-marketplace` | `sebbpro-ai-marketplace` |
| Plugin = one engagement phase | `sebbpro-<phase>`, lowercase kebab-case, phase as a single noun. The `sebbpro-` prefix names the sender and avoids clashes with other plugins in the client's account. Folder `plugins/<plugin>` is identical to `name` in `plugin.json` | `sebbpro-discovery` |
| Skill | Short (1–2 words), the **action or artefact**, lowercase kebab-case. **No** sender, phase or `ai-` prefix — the plugin already supplies them. Folder name = `name` in the frontmatter | `intake` |
| Output format id (`format:` front matter) | `<topic>-<artefact>/<n>`, kept stable across renames | `ai-discovery-intake/1` |

Further rules:
- Install ID is `<plugin>@<marketplace>`, e.g. `sebbpro-discovery@sebbpro-ai-marketplace`.
- No internal vocabulary (see rule 3) and no technical terms in plugin or skill names.
- **Renaming a plugin or skill breaks every existing install** — decide names before a client installs; after that rename only with a version bump and a note to the clients.
- A new skill that fits an existing phase goes into that phase's plugin; a new phase is a new plugin.

