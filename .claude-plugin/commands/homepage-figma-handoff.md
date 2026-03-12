---
description: Turn a homepage brief or IA into Figma MCP-ready layout, token, and component instructions.
argument-hint: Paste the brief or IA, plus any brand direction, references, and device priorities.
---

Transform the user's input into a Figma MCP handoff spec.

<input>
$ARGUMENTS
</input>

Your job is to create an output that can be used directly by another agent controlling Figma.

Produce these sections.

1. Frame plan
- Desktop frame size
- Mobile frame size
- Variants or alternate states that must exist

2. Layout system
- Grid definition
- Spacing scale
- Section-by-section layout instructions

3. Design tokens
- Colors with semantic names
- Typography scale
- Radius, shadow, border, and surface rules

4. Component inventory
- Navbar, hero, social proof, feature blocks, CTA blocks, footer, and any domain-specific modules
- Variants and states for each component

5. Copy placeholders
- Headlines, body copy, CTA labels, trust signals, and proof content

6. MCP execution checklist
- Ordered steps another agent should follow inside Figma
- Naming conventions for pages, frames, components, and styles

Write the result to docs/homepage-figma-spec.md if that file does not already exist, or update it if it does.

Constraints.
- Optimize for implementation clarity over visual theory.
- Keep desktop and mobile aligned as one system.
- If the brief is vague, make assumptions explicit instead of hiding them.