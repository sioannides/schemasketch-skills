---
name: schemasketch
description: Use when the user wants to design, edit, validate, import, or export a database schema/ER diagram — creates and manages SchemaSketch diagrams via its MCP server, and can convert to/from real SQL DDL, Laravel migrations, Mermaid erDiagram, or PlantUML entity syntax.
---

# SchemaSketch

SchemaSketch (https://schemasketch.dev) is a free, hosted database diagram
tool. Diagrams are written in a small DBML-like text language, rendered
live, and stored on the user's account. This skill covers working with it
via its MCP server rather than the web UI.

## Setup

Fetch and follow https://schemasketch.dev/agent-setup/prompt.md — it's written
directly for an agent (not a human) and covers getting a token, picking the
right connection method for whichever client you are (a hosted HTTPS
endpoint for Claude Code/Cursor/etc., a one-click extension for Claude
Desktop, or a local stdio process for anything else), and verifying the
connection. Full reference: https://schemasketch.dev/docs#mcp-docs — auth
details: https://schemasketch.dev/auth.md

## Workflow

1. Call `get_dbml_syntax_guide` once per session before writing any DBML —
   it returns the exact syntax (table/column attributes, ref types, enums,
   subject areas) with a full example.
2. Draft the DBML for what the user described — or, if they handed you
   existing SQL DDL, a Mermaid `erDiagram`, or a PlantUML `entity` diagram
   instead, run it through `import_sql`/`import_mermaid`/`import_plantuml`
   first to get DBML back.
3. Call `validate_dbml` on it and fix anything flagged before saving —
   `create_diagram`/`update_diagram` do not validate for you.
4. `create_diagram` (name + dbml_source) to save it, or `update_diagram`
   to edit an existing one (fetched first via `get_diagram` if editing
   rather than replacing).
5. On request, convert it back out: `export_sql` (dialect:
   postgres/mysql/mssql/oracle), `export_laravel_migrations`,
   `export_mermaid`, or `export_plantuml` — all four accept either a saved
   `diagram_id` or raw `dbml_source` directly, so a schema doesn't need to
   be saved first just to export it.

## Tools available

`get_dbml_syntax_guide`, `list_diagrams`, `get_diagram`, `validate_dbml`,
`create_diagram`, `update_diagram`, `delete_diagram`, `export_sql`,
`export_laravel_migrations`, `export_mermaid`, `export_plantuml`,
`import_sql`, `import_mermaid`, `import_plantuml`. Full parameter
reference: https://schemasketch.dev/docs#mcp-docs and
https://schemasketch.dev/.well-known/mcp/server-card.json
