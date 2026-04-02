---
name: raycast-extension-docs
description: "Guidance for building, debugging, and publishing Raycast extensions using the Raycast documentation set. Use when Codex needs to create or modify Raycast extensions (React/TypeScript/Node), consult Raycast API reference or UI components, build AI extensions, handle manifest/lifecycle/preferences, troubleshoot issues, or prepare/publish extensions to the Raycast Store or Teams."
---

# Raycast Extension Docs

## Overview

Use the bundled Raycast documentation under `references/` as the source of truth for APIs, patterns, and policies. Route requests to the right section, load only the needed files, and apply the guidance to the user's task.

## Quick Routing

- Start with `references/SUMMARY.md` to locate the right doc page.
- Use `references/README.md` for the general introduction and platform overview.
- Use `references/basics/` for step-by-step guides (getting started, create, debug, publish).
- Use `references/api-reference/` for API details and component usage.
- Use `references/api-reference/user-interface/` for UI components (List, Form, Detail, Action Panel, etc.).
- Use `references/ai/` and `references/api-reference/ai.md` for AI extension guidance.
- Use `references/examples/` for real-world extension patterns.
- Use `references/information/` for terminology, manifest, lifecycle, file structure, best practices, tools, and security.
- Use `references/utils-reference/` for utility helpers and patterns.
- Use `references/teams/` for private/team extension workflows.
- Use `references/migration/` and `references/changelog.md` for version changes and breaking updates.
- Use `references/faq.md` for quick clarifications.

## Working Approach

1. Identify the user's goal and map it to the most relevant section in `references/SUMMARY.md`.
2. Open the specific doc file(s) and extract only the details needed to answer or implement.
3. Cross-check API usage against `references/api-reference/` and best practices in `references/information/best-practices.md`.
4. When building UI, verify component props and patterns in `references/api-reference/user-interface/`.
5. When shipping or collaborating, confirm publish/team steps in `references/basics/` or `references/teams/`.
6. Validate the extension before publishing:
   - Run `npm run dev` to test locally and confirm no build errors.
   - Check `package.json` manifest fields against `references/information/manifest.md`.
   - Verify store requirements in `references/basics/prepare-an-extension-for-store.md`.
7. If build or runtime errors occur, consult `references/faq.md` and `references/information/developer-tools.md` for common fixes.

## Common Tasks

### Scaffold a new extension

```bash
npx create-raycast-extension@latest --name my-extension --template detail
cd my-extension && npm install && npm run dev
```

See `references/basics/create-your-first-extension.md` for the full walkthrough.

### Minimal List command

```tsx
import { List } from "@raycast/api";

export default function Command() {
  return (
    <List>
      <List.Item title="Hello" subtitle="World" />
    </List>
  );
}
```

See `references/api-reference/user-interface/list.md` for all List props and patterns.

## Notes

- Keep answers aligned with the docs; call out when guidance is inferred or when the docs are silent.
- If the user asks about behavior changes, consult `references/migration/` and `references/changelog.md`.
