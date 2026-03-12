---
description: Turn a webpage, website, or web service brief into Figma MCP-ready frames, tokens, components, and execution steps.
argument-hint: Paste the brief or IA, plus brand direction, references, and target devices.
---

Transform the user's input into a Figma MCP handoff spec.

<input>
$ARGUMENTS
</input>

First detect whether the project is a webpage, website, or webservice.

Produce these sections.

1. Frame inventory
- Required desktop frames
- Required mobile frames
- Required key states, modals, overlays, empty states, loading states, and error states when relevant

2. Layout system
- Grid definition
- Spacing scale
- Page or screen-by-screen layout instructions
- Responsive behavior rules

3. Design tokens
- Semantic colors
- Typography scale
- Radius, border, shadow, surface, and motion rules

4. Component inventory
- Shared primitives
- Navigation patterns
- Content modules
- Form patterns
- Data display or dashboard modules when relevant
- Variants and interaction states for each component

5. Copy placeholders
- Headlines, labels, body copy, CTA labels, trust signals, helper text, system messages, and errors

6. MCP execution checklist
- Ordered steps another agent should follow inside Figma
- Naming conventions for pages, frames, components, variants, and styles

Write the result to docs/figma-spec.md if that file does not already exist, or update it if it does.

Constraints.
- Optimize for implementation clarity over visual theory.
- Keep desktop and mobile aligned as one system.
- If the brief is vague, make assumptions explicit instead of hiding them.