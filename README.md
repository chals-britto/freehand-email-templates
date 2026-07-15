# Freehand Email Templates

Source of truth for Freehand notification emails. **Start from the golden master — don't generate HTML from scratch.**

## What's here
| Path | What |
|---|---|
| `templates/Email_Template_v5.html` | Golden master — every approved component, each marked `DELETE IF UNUSED` |
| `system-prompt-v5.md` | Prompt for Claude (Cursor / VS Code) — asks smart questions, then assembles from the master |
| `assets/` | Hosted images referenced by the templates (see below) |

## How to build an email
1. Copy `templates/Email_Template_v5.html`.
2. Delete the blocks you don't need. Fill the `[SLOTS]`.
3. Change nothing else — no new colours, components, layouts, or wording. Rules are in the system prompt.

## Assets (must be PNG, must be public)
Email clients (Gmail, Outlook) **do not render SVG or base64 images**, and they fetch images **unauthenticated**. So the logo must be:
- a **PNG** (white-on-transparent, exported @2x from Figma), and
- served from a **public** URL.

Drop the export here as `assets/freehand-logo-white.png`, then reference it in the footer:

```
https://chals-britto.github.io/freehand-email-templates/assets/freehand-logo-white.png
```

The decorative watermark is intentionally **not** used in email (Outlook ignores CSS background images).

## Brand tokens (quick reference)
Background `#F3F6FC` · Card `#FFFFFF` · Ink `#0F172A` · Body `#334155` · Muted `#5B6B82` · Divider `#E5E9EF` · Footer `#153F69` · CTA `#FE6200` · Link `#1F5D9C` · Danger `#B42318` (expiry only). Font: Open Sans.
