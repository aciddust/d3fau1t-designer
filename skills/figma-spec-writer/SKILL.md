---
name: figma-spec-writer
description: "Use when: a product structure or IA exists and you need to produce a Figma MCP-ready design spec. Outputs frames, design tokens, components, copy placeholders, and a step-by-step MCP execution checklist."
---

# Figma Spec Writer Skill

## Purpose

Convert an IA or project brief into a Figma MCP-ready design specification.

## Inputs

Product structure (docs/product-structure.md) or inline IA, plus brand direction and device priorities.

## Steps

1. Detect project type and derive frame inventory.
   - List required desktop frames.
   - List required mobile frames.
   - List required states: modals, overlays, empty, loading, error.

2. Produce layout system.
   - Grid: columns, gutter, margin.
   - Spacing scale: base unit and step values.
   - Responsive breakpoints.

3. Produce design tokens.
   - Colors with semantic names: background, surface, primary, secondary, text, border, error, success.
   - Typography: font family, size scale, weight, line height.
   - Radius, border, shadow, and motion values.

4. Produce component inventory.
   - Navigation, hero, content modules, form patterns, CTA blocks, feedback elements.
   - For each: variants and interaction states.

5. Produce copy placeholder map.
   - One entry per text element: key, location, type, placeholder text.

6. Produce MCP execution checklist.
   - Ordered steps a Figma agent should follow.
   - Naming conventions for pages, frames, layers, components, and styles.

## Output

Write to docs/figma-spec.md.
