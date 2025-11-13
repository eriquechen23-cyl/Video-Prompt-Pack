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
- `video-creation/assets/` – Placeholder folders for shared references (faces, flipbooks, LUTs, audio).
- `video-creation/projects/` – Project-specific configurations and scripts following the naming convention.

## Workflow Guidelines

1. **Always read `AGENT.md` files** in the relevant directory tree before making changes. Project prompts must embed any referenced `_core` or `_stylepacks` content directly inside `prompt.md` (no shortcuts or links).
2. **Duplicate and adapt templates** from `_core` when drafting new prompts. Keep the structure intact so downstream tools can parse scene beats and technical specs.
3. **Select or create a style pack** in `_stylepacks/` that matches the target aesthetic. Add new packs (e.g., `frost_gambler`) when the look or FX palette differs from existing sets.
4. **Store only `prompt.md`** in each project directory. Omit meta files unless future `AGENT.md` instructions specify otherwise.
5. **Version projects** using the `YYYY-MM-DD_slug_v0X` pattern, logging seeds and sync parameters inside the prompt if needed for reproducibility.

## Creating a 15-Second Prompt

- Draft a one-sentence hook summarizing the concept.
- Fill in the master prompt using the embedded template, specifying duration (15s), framing, and tonal notes.
- Break the video into clearly timed scene beats (e.g., 12 beats × 1.2s) that map to the narrative arc.
- Include VFX, audio, and camera directives aligned with the chosen style pack.
- Conclude with QA or delivery notes if requested by the project brief.
