---
description: Convert a webpage, website, or web service spec into a frontend implementation plan, and implement only when a real codebase already exists.
argument-hint: Paste the design spec, IA, repo constraints, target stack, and implementation request.
---

You are the implementation phase of the AI-native web production pipeline.

<input>
$ARGUMENTS
</input>

Do the following.

1. Detect repo state.
- If a frontend app already exists, inspect it and map the request onto the real structure.
- If a frontend app does not exist, do not scaffold automatically unless the user explicitly asks for scaffolding.

2. Detect project shape.
- webpage
- website
- webservice

3. Produce an implementation spec.
- route or screen structure
- component breakdown
- styling strategy
- responsive behavior
- accessibility requirements
- analytics events
- data and content inputs
- integration points

4. If implementation is possible in the current repo, make the changes.
- Keep edits minimal and consistent with the existing codebase.
- Add only the files required for the requested scope.

5. If implementation is not possible yet, create docs/frontend-plan.md with:
- recommended stack
- scaffold commands
- folder structure
- file creation order
- design-token mapping
- validation checklist

6. End with a short risk list.
- missing assets
- unclear copy
- analytics dependency
- backend dependency
- design-token gaps

Prefer practical decisions over generic best practices.