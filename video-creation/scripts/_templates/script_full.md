# Script Blueprint

> Duplicate this file into `video-creation/scripts/YYYY-MM-DD_slug_v0X/script.md` when starting a new project. Follow the `YYYY-MM-DD_slug_v0X` naming pattern to stay aligned with `projects/` outputs.

---

## Project Overview

- **Project ID**: `YYYY-MM-DD_slug_v0X`
- **Source Style Pack**: `<_stylepacks/look>/<_stylepacks/lens>/<_stylepacks/safety>`
- **Core Prompt Blocks to Embed**: `<_core/master_prompt | _core/story_beats | _core/audio | _core/qa>`
- **Metadata File (optional)**: `metadata.json` mapping script fields to prompt sections.

## One-Sentence Concept

Summarize the narrative hook in one sentence that sells the tone, genre, and stakes.

## Act & Beat Outline

Describe the full narrative progression. Use act headers with beat-by-beat notes. Call out the `_core` sections that will map to each beat (e.g., `Master Prompt > Scene Beats > Beat 03`).

### Act I – Setup
- **Beat**: Title the beat and describe the action, emotion, and goal.
- **Visual Intent**: Key framing, lens, or motion notes that must appear in the prompt.
- **Audio Intent**: Music, SFX, VO cues tied to `_core/audio` blocks.

### Act II – Confrontation
- Repeat beat entries until the middle escalation is fully covered.

### Act III – Resolution
- Repeat beat entries until the conclusion and CTA are captured.

## Character & Scene Roster

List every character, performer, and major prop with quick descriptors and reference IDs. Include primary locations or sets so the prompt can reintroduce them consistently.

## Visual Language & Style Notes

Document the chosen look, lens, color pipeline, FX, and safety settings drawn from `_stylepacks/`. Note any overrides or blends between packs.

## Camera & Motion Plan

Shot types, camera moves, frame rates, and transitions. Reference `_core/camera_*.md` segments that must be embedded.

## Audio & Voice Strategy

Music direction, voiceover cadence, foley, and mix notes that will be carried into `_core/audio` when drafting the prompt.

## Pace & Timing Grid

Break the runtime into time-coded beats (e.g., `00:00–00:03 Opening tableau`). Include rhythm notes so the prompt’s scene list preserves timing.

## Safety & Compliance Checklist

Document any compliance, content rating, or platform notes that need verbatim inclusion from `_stylepacks/*/safety.md`.

## Prompt Mapping Checklist

- [ ] `projects/<project>/prompt.md` header references this script.
- [ ] All `_core` segments cited above are embedded without omission.
- [ ] Style pack selections are mirrored in the prompt’s look, lens, and safety sections.
- [ ] Beat descriptions convert cleanly into the Master Prompt scene hierarchy.
- [ ] Version number matches between script and prompt directories.

## Revision Log

| Version | Date       | Notes |
| ------- | ---------- | ----- |
| v01     | YYYY-MM-DD | Initial draft. |

