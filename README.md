# Video Prompt Pack

This repository stores reusable templates and style packs for video prompt creation.

## Structure

- `video-creation/_core/` – Global templates for prompts, scene blocks, VFX, audio, delivery presets, and QA.
- `video-creation/_stylepacks/` – Style pack definitions for different looks and technical setups.
  - `real_cinema/`
  - `sci_fi_realism/`
  - `anime_fantasy/`
  - `arcane_gambler/`
  - `frost_gambler/`
- `video-creation/projects/` – Prompt deliverables (`prompt.md`) stored per project directory using the `YYYY-MM-DD_slug_v0X` pattern.
- `video-creation/scripts/` – Script workspaces that mirror `projects/` naming so each prompt has a one-to-one, versioned narrative source.

## Workflow Guidelines

1. **Always read `AGENT.md` files** in the relevant directory tree before making changes. Project prompts must embed any referenced `_core` or `_stylepacks` content directly inside `prompt.md` (no shortcuts or links).
2. **Start every project in `video-creation/scripts/`** by duplicating `_templates/script_full.md` into `scripts/YYYY-MM-DD_slug_v0X/script.md`. Capture logline, beat sheet, pacing, and explicit references to the `_core` and `_stylepacks` elements you will embed later.
3. **Select or create a style pack** in `_stylepacks/` that matches the target aesthetic. Document the chosen look/lens/safety inside the script so the prompt can quote them verbatim.
4. **Promote the script into a prompt** by copying the necessary `_core` blocks and style pack content into `projects/YYYY-MM-DD_slug_v0X/prompt.md`. Add a plain-text header noting the source script path (e.g., `來源劇本：scripts/.../script.md`).
5. **Store only `prompt.md`** in each project directory. Keep script drafts, metadata, or planning files inside the matching `scripts/` folder.
6. **Version scripts and prompts together** using the `YYYY-MM-DD_slug_v0X` pattern, incrementing the version when either artifact changes so history stays synchronized.

### Optional Automation Metadata

- If you plan to automate script-to-prompt conversion, add a `metadata.json` (or `.yml`) file alongside `script.md` in the project’s `scripts/` directory. Use it to map script sections to prompt targets so CODEX or other tooling can process the handoff without touching the `projects/` outputs.

## Creating a 15-Second Prompt

- Draft a one-sentence hook summarizing the concept.
- Fill in the master prompt using the embedded template, specifying duration (15s), framing, and tonal notes.
- Break the video into clearly timed scene beats (e.g., 12 beats × 1.2s) that map to the narrative arc.
- Include VFX, audio, and camera directives aligned with the chosen style pack.
- Conclude with QA or delivery notes if requested by the project brief.
