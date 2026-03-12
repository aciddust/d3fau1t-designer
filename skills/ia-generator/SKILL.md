---
name: ia-generator
description: "Use when: a validated brief exists and you need to produce an information architecture, sitemap, or user flow. Adapts output shape based on whether the project is a webpage, website, or webservice."
---

# IA Generator Skill

## Purpose

Generate information architecture, page or screen inventory, and primary user flows from a validated project brief.

## Inputs

A filled project brief (docs/project-brief.md or inline).

## Steps

1. Detect project type.

2. For a **webpage**:
   - Define section order and purpose.
   - Map message hierarchy from top to CTA.
   - Identify experiment points.

3. For a **website**:
   - Produce a sitemap with page names, URLs, and purpose.
   - Define navigation model and key templates.
   - Map 2 to 3 primary user flows with entry, steps, and goal.

4. For a **webservice**:
   - Define core jobs-to-be-done.
   - Produce a screen inventory with screen names, types, and entry points.
   - Map critical flows: onboarding, primary job, recovery, empty state.
   - Define key state transitions.

5. Output a product structure document.

## Output

Write to docs/product-structure.md.
