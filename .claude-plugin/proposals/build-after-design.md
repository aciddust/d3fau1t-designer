---
title: Generate Frontend Build Plan
trigger: docs/figma-spec.md exists and docs/frontend-plan.md does not yet exist.
command: /web-build
---

Your design spec is ready. Run the build step to produce a frontend implementation plan.

**What this will produce**

- Route or screen structure
- Component breakdown
- Styling strategy and token mapping
- Responsive behavior notes
- Analytics event list
- Scaffold commands and folder structure (when no codebase exists)
- Risk list

**Run it now**

```md
/web-build
[reference docs/figma-spec.md and docs/product-structure.md, specify target stack and any repo constraints]
```
