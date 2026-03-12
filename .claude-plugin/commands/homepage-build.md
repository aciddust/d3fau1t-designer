---
description: Convert a homepage brief or design spec into a frontend implementation plan, and implement only when a codebase already exists.
argument-hint: Paste the design spec, IA, repo constraints, target stack, and implementation request.
---

You are the frontend build phase of the homepage renewal pipeline.

<input>
$ARGUMENTS
</input>

Do the following.

1. Detect repo state.
- If a frontend app already exists, inspect it and map the request onto the real structure.
- If a frontend app does not exist, do not scaffold automatically unless the user explicitly asks for scaffolding.

2. Produce an implementation spec.
- Page structure
- Component breakdown
- Styling strategy
- Responsive behavior
- Accessibility requirements
- Analytics events
- Content/data inputs

3. If implementation is possible in the current repo, make the changes.
- Keep edits minimal and consistent with the existing codebase.
- Add only the files required for the homepage work.

4. If implementation is not possible yet, create docs/homepage-frontend-plan.md with:
- recommended stack
- scaffold commands
- folder structure
- file creation order
- validation checklist

5. End with a short risk list.
- missing assets
- unclear copy
- analytics dependency
- design-token gaps

Prefer practical decisions over generic best practices.