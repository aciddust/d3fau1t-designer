---
name: brief-intake
description: "Use when: a user provides a raw web project brief that needs validation and structuring before running the pipeline. Extracts and fills required fields, surfaces gaps, and returns a structured brief ready for the next pipeline stage."
---

# Brief Intake Skill

## Purpose

Validate and structure a raw web project brief into the canonical format required by this plugin's pipeline commands.

## Inputs

Raw user brief in any format — prose, bullet points, partial form, or template.

## Steps

1. Extract these fields from the input.
   - project_type: webpage, website, or webservice
   - business_goal
   - target_audience
   - success_event (primary CTA or conversion)
   - scope (required pages or screens)
   - brand_direction
   - technical_constraints (stack, existing codebase, deployment)
   - content_inputs (existing copy, assets, data sources)
   - delivery_constraints (deadline, review owner)

2. For each missing required field, ask one targeted question.
   Required fields: project_type, business_goal, target_audience, success_event.

3. Return the structured brief as a filled version of `.claude-plugin/templates/web-project-brief.md`.

4. Append an Assumptions section listing inferred values.

## Output

A filled brief document ready to feed into `/web-product-pipeline`.
