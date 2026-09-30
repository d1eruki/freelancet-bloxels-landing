# Figma Landing Implementation Rules

For section-by-section work, use `/Users/dieruki/.codex/agent-guidance/figma/references/design-to-code-sections.md`. This repository keeps only its own exceptions below.

## Stack and export

- Preserve the static HTML/CSS/JS stack by default. Convert React/Tailwind-like output into local CSS classes unless the user explicitly asks to use Tailwind.
- When Tailwind is explicitly requested, keep exported utility classes for exact widths, heights, gaps, padding, offsets, radii, shadows, text sizes, and line heights. Add only a minimal bridge stylesheet for invalid export utilities such as `bg-linear-*`, `size-`, or malformed radial-gradient stops.
- Do not replace a Tailwind-export composition with hand-authored approximations unless the export is structurally impossible to render.

## Acceptance

- Match the desktop 1440px frame first; responsive rules must not corrupt desktop fidelity.
- `git diff --check` must pass after changes.
