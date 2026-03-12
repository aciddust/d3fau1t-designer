---
description: Run an AI-native homepage renewal pipeline from brief to IA, Figma handoff, frontend build spec, and experiment plan.
argument-hint: Paste a homepage brief, KPI, target audience, brand constraints, and preferred stack.
---

You are running the team's homepage renewal pipeline.

Use the user's arguments below as the source brief.

<brief>
$ARGUMENTS
</brief>

Execute this workflow in order.

1. Validate the brief.
- Extract business goal, primary audience, value proposition, conversion KPI, proof points, brand constraints, and technical constraints.
- If key inputs are missing, ask only the minimum blocking questions.

2. Produce information architecture.
- Create a concise sitemap for the homepage only.
- Define section order, purpose of each section, required content, and target user action.
- Include 2 to 3 user flows and 3 experiment hypotheses.

3. Produce Figma MCP handoff instructions.
- Describe the desktop and mobile frame structure.
- Define section layout, grid, spacing rhythm, typography system, color tokens, component list, and copy placeholders.
- Make the output specific enough that another agent can recreate the design in Figma with MCP.

4. Produce frontend build spec.
- Recommend the most appropriate stack among Next.js, React, and SvelteKit based on the brief.
- Define route scope, component tree, responsive behavior, accessibility requirements, animation constraints, analytics events, and content model.
- If an app already exists in the repo, propose concrete implementation steps against the existing structure.
- If no app exists, write a scaffold plan only. Do not invent files outside the documented plan unless the user explicitly asks to scaffold.

5. Produce review loop.
- Define a fast review cycle with inputs, owner, artifact, and approval criteria for each step.
- Include a deploy-preview checklist and A/B test setup checklist.

Write or update these files when useful.
- docs/homepage-brief.md
- docs/homepage-ia.md
- docs/homepage-figma-spec.md
- docs/homepage-build-spec.md
- docs/homepage-experiments.md

Response rules.
- Be concrete, not inspirational.
- Prefer tables where they improve scanability.
- Surface assumptions explicitly.
- If the brief conflicts with itself, stop and call out the conflict.