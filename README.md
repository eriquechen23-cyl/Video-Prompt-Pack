# Video Prompt Pack

This repository stores reusable templates and style packs for video prompt creation.

## Structure

- `video-creation/_core/` – Global templates for prompts, scene blocks, VFX, audio, delivery presets, and QA.
- `video-creation/_stylepacks/` – Style pack definitions for different looks and technical setups.
  - `real_cinema/`
  - `sci_fi_realism/`
  - `anime_fantasy/`
- `video-creation/assets/` – Placeholder folders for shared references (faces, flipbooks, LUTs, audio).
- `video-creation/projects/` – Project-specific configurations and scripts following the naming convention.

## Getting Started

1. Duplicate the templates in `_core` to draft new prompts and scene blocks.
2. Reference style packs in project `meta.yml` files to keep visual and technical settings consistent.
3. Track updates by versioning projects (e.g., `v02`, `v03`) while logging seeds and sync parameters.
