---
name: seekdb-docs
description: Provide SeekDB official docs (built-in en-US/zh-CN content + menu maps). Use for docs lookup across SQL/SDK APIs, vector/hybrid search, deployment/ops, integrations (MCP/plugins), etc.
---

# SeekDB Docs Lookup & Code Mapping

## Sources of truth

- en-US docs content: `seekdb-docs/seekdb-docs/en-US/`
- en-US menu map (info architecture): `seekdb-docs/seekdb-docs/.menu_map_en-US.yml`
- zh-CN docs content (fallback): `seekdb-docs/seekdb-docs/zh-CN/`
- zh-CN menu map: `seekdb-docs/seekdb-docs/.menu_map_zh-CN.yml`
- Quick index: `reference.md`

Note: This skill prefers en-US docs by default, and falls back to zh-CN when the en-US page is missing.

## Default workflow (token-efficient)

- Use the menu map to locate the section path (e.g. `200.develop → 600.search → 300.vector-search`).
- Search under `seekdb-docs/seekdb-docs/en-US/` with `Grep` or filename to find the target `.md`.
- Read only the matched small file(s) or small slices (use offset/limit when needed), and extract: definition, steps, examples, and gotchas.
- If the en-US page is not found, repeat the same search under `seekdb-docs/seekdb-docs/zh-CN/`.

## Common entry points

- Docs overview: `seekdb-docs/seekdb-docs/en-US/10.doc-overview.md`
- Get started (SDK/SQL/AI Coding): `seekdb-docs/seekdb-docs/en-US/100.get-started/`
- Vector search: `seekdb-docs/seekdb-docs/en-US/200.develop/600.search/300.vector-search/`
- Hybrid search: `seekdb-docs/seekdb-docs/en-US/200.develop/600.search/500.hybrid-search.md`
- SQL reference: `seekdb-docs/seekdb-docs/en-US/450.reference/200.sql/`
- Integrations - MCP: `seekdb-docs/seekdb-docs/en-US/300.integrations/600.mcp/200.seekdb-mcp-server.md`

## Output requirements

- Provide the shortest path and the conclusion; include at most 1 key file path when needed.
- When quoting docs, prefer quoting the original paragraph and include the source file path.
- Avoid generic explanations; prioritize: where it is + how to do it + what to watch out for.

## Quick update guide: refresh `references/doc-index.md` after docs changes

Use this when `seekdb-docs/{en-US,zh-CN}` or `.menu_map_*.yml` changes, to quickly sync the human-facing index.

### Inputs (sources of truth)

- Menu maps (IA): `seekdb-docs/seekdb-docs/.menu_map_en-US.yml`, `seekdb-docs/seekdb-docs/.menu_map_zh-CN.yml`
- Docs roots: `seekdb-docs/seekdb-docs/en-US/`, `seekdb-docs/seekdb-docs/zh-CN/`

### Steps (fast + safe)

- Check whether the doc roots still exist and roughly how many pages there are.
- For each main section in `.menu_map_*.yml` (Get started / Develop / Integrations / Guides / Reference / Tutorials / Demos), pick 1-2 stable entry pages (prefer “overview” pages).
- Verify each referenced path exists (prefer en-US; if missing, fall back to zh-CN).
- Update `references/doc-index.md`:
  - Keep it short: roots + main entry points + 2-step “how to locate a page”.
  - Avoid deep trees; keep only the most common entry points.

### Recommended entry points to keep (update if renamed/moved)

- Docs overview: `seekdb-docs/seekdb-docs/en-US/10.doc-overview.md` (fallback: `seekdb-docs/seekdb-docs/zh-CN/10.doc-overview.md`)
- Get started overview: `seekdb-docs/seekdb-docs/en-US/100.get-started/10.overview/10.seekdb-overview.md`
- Embedded SDK quickstart: `seekdb-docs/seekdb-docs/en-US/100.get-started/50.use-seekdb-with-sdk/25.using-seekdb-in-python-sdk.md`
- Server mode quickstart: `seekdb-docs/seekdb-docs/en-US/100.get-started/100.use-seekdb-with-sql/10.deploy-seekdb-testing-environment.md`
- Develop overview: `seekdb-docs/seekdb-docs/en-US/200.develop/10.overview/10.develop-overview.md`
- Vector search intro: `seekdb-docs/seekdb-docs/en-US/200.develop/600.search/300.vector-search/100.vector-search-intro.md`
- Hybrid search: `seekdb-docs/seekdb-docs/en-US/200.develop/600.search/500.hybrid-search.md`
- MCP: `seekdb-docs/seekdb-docs/en-US/300.integrations/600.mcp/200.seekdb-mcp-server.md`
- Deploy overview: `seekdb-docs/seekdb-docs/en-US/400.guides/400.deploy/50.deploy-overview.md`
- SQL reference entry: `seekdb-docs/seekdb-docs/en-US/450.reference/200.sql/100.sql-syntax/100.basic-elements/100.data-type/100.data-type-overview.md`
- Python SDK entry: `seekdb-docs/seekdb-docs/en-US/450.reference/900.sdk/10.pyseekdb-sdk/10.pyseekdb-sdk-get-started.md`
- Tutorial entry: `seekdb-docs/seekdb-docs/en-US/500.tutorials/100.create-ai-app-demo/100.build-kb-in-seekdb.md`
- Demos overview: `seekdb-docs/seekdb-docs/en-US/600.demos/10.demo-overview.md`
