# AI Agents — architecture diagrams

Two self-contained interactive HTML pages. Open either directly in a browser; there is no build step
and no external dependency.

| File | Shows |
|---|---|
| `perfexe-agents-architecture.html` | Who owns what: the Super Admin portal and catalog DB, the Agent Framework API and per-workspace DB, our web app, the third-party orchestrator and the LLM vendors — and which calls cross which boundary |
| `perfexe-agents-dataflow.html` | The same story as five stages of data: configured by PerfeXe → copied on hire → opened by the user (chat UI vs. step UI) → run by the orchestrator → stored in the workspace |

Both carry guided views (top-right), search, relationship tracing and a light/dark toggle.

## Regenerating

The `.json` files beside them are the source; the HTML is generated output. Do not hand-edit the HTML
— edit the spec and re-render with the `archify` skill:

```bash
node bin/archify.mjs deliver architecture agents-architecture.json perfexe-agents-architecture.html --quality showcase
node bin/archify.mjs deliver dataflow     agents-dataflow.json     perfexe-agents-dataflow.html     --quality showcase
```

Both specs currently pass at the `showcase` quality profile with no composition errors or warnings.

Narrative background lives in `docs/ai-agents-spec.md`; these are the pictures for it.
