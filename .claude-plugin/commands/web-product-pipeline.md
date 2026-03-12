---
description: Run an AI-native web production pipeline for a webpage, website, or web service from brief to UX structure, design handoff, frontend build plan, and validation.
argument-hint: Paste the product brief, target users, KPIs, brand constraints, content inputs, and preferred stack.
---

You are running the team's AI-native web production pipeline.

Use the user's arguments below as the source brief.

<brief>
$ARGUMENTS
</brief>

First classify the project as one of these.
- webpage
- website
- webservice

Then execute this workflow in order.

1. Validate the brief.
- Extract business goal, target audience, conversion goal, success KPI, scope, required pages or screens, content dependencies, brand constraints, technical constraints, and launch constraints.
- If key inputs are missing, ask only the minimum blocking questions.

2. Produce product structure.
- For a webpage: define section architecture, message hierarchy, CTA structure, and experiment hypotheses.
- For a website: define sitemap, key templates, page purposes, navigation model, and major user flows.
- For a webservice: define core jobs-to-be-done, information architecture, primary flows, critical screens, state changes, and feature boundaries.

3. Produce Figma MCP handoff instructions.
- Define frame inventory for desktop and mobile.
- Define grid, spacing, tokens, components, copy placeholders, and variant states.
- Make the output specific enough that another agent can recreate the design in Figma with MCP.

4. Produce implementation plan.
- Recommend the most appropriate stack based on scope and constraints.
- Define route or screen scope, component tree, responsive behavior, accessibility requirements, analytics events, content model, and integration points.
- If an app already exists in the repo, propose concrete implementation steps against the existing structure.
- If no app exists, write a scaffold plan only unless the user explicitly asks to scaffold.

5. Produce operating loop.
- Define review inputs, owner, artifact, approval criteria, and turnaround target for each phase.
- Include preview deploy checklist, QA checklist, analytics verification checklist, and experiment checklist.

Write or update these files when useful.
- docs/project-brief.md
- docs/product-structure.md
- docs/figma-spec.md
- docs/build-spec.md
- docs/validation-plan.md

Response rules.
- Be concrete and execution-oriented.
- Explicitly separate facts, assumptions, and open questions.
- Prefer tables where they improve scanability.
- If the brief conflicts with itself, stop and call out the conflict.