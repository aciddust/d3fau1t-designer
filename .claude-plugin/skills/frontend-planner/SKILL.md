---
name: frontend-planner
description: "Use when: a design spec or IA exists and you need to produce a frontend implementation plan. When a codebase already exists, maps changes onto the real structure. When no codebase exists, produces a scaffold plan only."
---

# Frontend Planner Skill

## Purpose

Produce a frontend implementation plan from a design spec or IA. Implement only when a real codebase already exists in the repository.

## Inputs

- docs/figma-spec.md or docs/product-structure.md
- Target stack preference
- Existing codebase path (if any)

## Steps

1. Detect repo state.
   - If a frontend app exists, inspect the folder structure and map the request onto it.
   - If no app exists, produce a scaffold plan only. Do not create files without explicit user request.

2. Detect project type: webpage, website, or webservice.

3. Produce implementation spec.
   - Route or screen list with file paths.
   - Component tree aligned to design spec.
   - Styling strategy and token mapping.
   - Responsive behavior notes per breakpoint.
   - Accessibility requirements.
   - Analytics events list.
   - Data and content inputs.
   - External integration points.

4. If codebase exists: make the changes. Keep edits minimal.

5. If no codebase: write docs/frontend-plan.md with:
   - Recommended stack and version
   - Scaffold commands (e.g., `npx create-next-app`)
   - Folder structure
   - File creation order
   - Design token mapping table
   - Validation checklist

6. Append a risk list: missing assets, unclear copy, analytics dependency, backend dependency, design-token gaps.

## Output

Write to docs/frontend-plan.md or docs/build-spec.md.
