[Back to README](../README.md)

# Diagrams

This folder contains editable Mermaid source files for the case-study diagrams. GitHub will render Mermaid diagrams embedded in Markdown pages; standalone `.mmd` files are included so the diagrams can be exported to PNG/SVG later.

| Mermaid Source | Optional Export | Purpose |
| --- | --- | --- |
| [`architecture.mmd`](architecture.mmd) | `architecture.png` | System architecture and component boundaries |
| [`n8n-workflow.mmd`](n8n-workflow.mmd) | `n8n-workflow.png` | Queue processing and platform lane routing |
| [`publishing-sequence.mmd`](publishing-sequence.mmd) | `publishing-sequence.png` | End-to-end publish request lifecycle |
| [`rpa-state-machine.mmd`](rpa-state-machine.mmd) | `rpa-state-machine.png` | RPA job states and human intervention states |
| [`data-model.mmd`](data-model.mmd) | `data-model.png` | Core entities and relationships |
| [`adapter-routing.mmd`](adapter-routing.mmd) | `adapter-routing.png` | Manual, RPA, API, and partner-tool routing |

## Export Guidance

Use Mermaid CLI or a Mermaid-compatible editor if image exports are needed:

```bash
mmdc -i diagrams/architecture.mmd -o diagrams/architecture.png
```

Do not add credentials, account identifiers, private URLs, or real content data to exported diagrams.

