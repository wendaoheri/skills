---
name: rich-html-output
description: Generates beautiful, styled HTML documents instead of raw markdown for complex structured output — design docs, architecture specs, product analysis, data reports, research summaries. Activated automatically when output would span 3+ sections, contain tables, code blocks, or complex hierarchy. Also triggers on phrases like "render as HTML", "show in browser", "export as HTML", "以HTML输出", "用浏览器打开", "生成报告", "输出文档", or the /render slash command. After generating, saves the file to ./output/ and opens it in the available terminal/browser environment, supporting cmux browser panes and Warp/macOS browser fallback. Never output raw markdown for substantial structured content — always use this skill instead.
---

# Rich HTML Output

You are in **rich-html-output** mode. Your job is to produce a complete, styled HTML document, save it, and open it in the current terminal/browser environment — not to emit markdown text into the conversation.

## When to Activate (Auto-Detection)

Activate this skill when the output:

- Has **3+ distinct sections** (would need multiple H2 headings)
- Contains **tables** or **comparison matrices**
- Contains **code blocks** with meaningful syntax
- Is a named deliverable: design doc, spec, report, analysis, proposal, review, 方案, 报告, 分析
- Would be **400+ words** of structured content

Skip for: casual replies, quick one-liners, short code snippets, conversational answers.

## Workflow

### Step 1 — Plan the document

Determine the document title and derive a kebab-case filename from it:
- "用户认证系统设计" → `user-auth-system-design.html`
- "PostgreSQL vs MongoDB 选型报告" → `postgresql-vs-mongodb-report.html`

### Step 2 — Generate the HTML

Produce a **complete, self-contained HTML file** using the template in `references/html-template.md`. Fill in all `{{PLACEHOLDER}}` values. For the body content, render all information as proper HTML — no markdown syntax inside the HTML. Sections become `<section>` elements with `id` attributes matching the TOC links.

Read `references/html-template.md` now for the full template and CSS.

Key content rules:
- **Tables**: use proper `<table><thead><tbody>` — never markdown tables
- **Code**: wrap in `<pre><code class="language-python">` (or appropriate language class)
- **Emphasis**: use `<strong>`, `<em>`, `<mark>` — never asterisks
- **Callouts**: use `<div class="callout">` for important notes, warnings, decisions
- **Language**: set `lang="zh-CN"` for Chinese docs, `lang="en"` for English
- **TOC**: always include when document has 3+ sections; omit for shorter docs
- **Diagrams**: use Mermaid.js — NEVER use ASCII/Unicode art for diagrams (see Diagram Guide below)

### Step 3 — Save the file

```bash
mkdir -p ./output
# Then write the HTML to ./output/<filename>.html
```

### Step 4 — Open in the current terminal/browser environment

```bash
html_path="$(pwd)/output/<filename>.html"
html_url="file://${html_path}"

if [ -n "${CMUX:-}" ] || [ -n "${CMUX_SESSION:-}" ] || [ "${TERM_PROGRAM:-}" = "cmux" ]; then
  cmux browser open-split "$html_url" || open "$html_path"
elif [ "${TERM_PROGRAM:-}" = "WarpTerminal" ] || [ -n "${WARP_IS_LOCAL_SHELL_SESSION:-}" ]; then
  open "$html_path"
elif command -v cmux >/dev/null 2>&1; then
  cmux browser open-split "$html_url" || open "$html_path"
else
  open "$html_path"
fi
```

If you are running the open command manually and the selected command fails, fall back to:
```bash
open "./output/<filename>.html"   # macOS system browser
```

Environment detection notes:
- **cmux**: prefer `cmux browser open-split` so the document appears in the cmux browser pane.
- **Warp**: detect `TERM_PROGRAM=WarpTerminal` or `WARP_IS_LOCAL_SHELL_SESSION`; use macOS `open` because Warp does not provide a cmux-style embedded browser pane.
- **Other terminals**: if `cmux` is installed, use it; otherwise use macOS `open`.

### Step 5 — Tell the user

After opening, say something like:
> 已生成 `./output/<filename>.html` 并已在当前环境中打开。

Don't paste the full HTML into the conversation — just confirm the file path and what was generated.

## Diagram Guide (Mermaid.js)

The HTML template includes Mermaid.js, which renders text definitions into crisp SVG diagrams. Use it everywhere a diagram would be clearer than text — don't fall back to ASCII art.

### How to embed a diagram

```html
<div class="mermaid">
flowchart LR
    Client -->|JWT| Gateway
    Gateway --> AuthService
    AuthService --> Redis[(Redis)]
    AuthService --> DB[(PostgreSQL)]
</div>
```

Mermaid initializes automatically on page load — no extra code needed.

### Diagram type selection

| Need | Mermaid type | Syntax hint |
|---|---|---|
| System / component architecture | `flowchart LR` or `flowchart TD` | boxes + arrows |
| API / interaction sequence | `sequenceDiagram` | `Client->>Server: request` |
| Database / entity model | `erDiagram` | `USER ||--o{ ORDER : places` |
| State machine | `stateDiagram-v2` | `[*] --> Idle` |
| User flow / process | `flowchart TD` | decision diamonds with `{label}` |
| Timeline / milestone | `timeline` | `section Phase1 \n Task A` |

### Style tips

- Keep diagrams focused — one concept per diagram, max ~15 nodes
- Use meaningful node labels; prefer Chinese text if the doc is in Chinese
- For architecture diagrams, group related services with `subgraph`

```html
<div class="mermaid">
flowchart LR
  subgraph 前端
    App[Web App]
  end
  subgraph 服务层
    API[API Gateway]
    Auth[认证服务]
  end
  App -->|HTTPS| API
  API --> Auth
</div>
```

## Terminal Compatibility Notes

cmux embeds a browser pane alongside terminal panes and reads `file://` URLs natively. The `open-split` command creates a vertical split with the browser on the right — if a browser pane is already open in the session, cmux reuses it. The browser supports modern HTML/CSS/JS, so all styling and syntax highlighting will render correctly.

If you need to reload after editing: `cmux browser reload` refreshes the current browser pane.

Warp should use the macOS browser fallback with `open ./output/<filename>.html`. This still opens the generated HTML immediately, but it appears in the system browser rather than an embedded terminal pane.
