[Back to README](../README.md)

# 09 Feature Documentation

## Feature Map

| Feature | Description |
| --- | --- |
| Queue-driven publishing | A Google Sheet row drives the workflow |
| Drive media handling | Media links are normalized before publishing |
| Platform lane routing | Each platform uses the most appropriate publishing adapter |
| Attended RPA | Automation fills forms but stops for safety states |
| Mobile automation | Android apps are controlled through Appium when needed |
| Status sync | Results are written back to exact source rows |
| Runbook-driven operations | Operators know when and how to intervene |

## Operator Workflow

1. Add content and media to the queue.
2. Mark the row ready.
3. Run or wait for the n8n workflow.
4. Review human intervention states if RPA stops.
5. Confirm final publishing when required.
6. Check status fields for completed, partially completed, or failed outcomes.

## Screenshot Placeholders

| File | What To Capture |
| --- | --- |
| `rednote-mobile-draft.png` | RedNote draft or filled post screen with demo content |
| `tiktok-mobile-publish.png` | TikTok mobile automation state with demo content |
| `artifacts-folder.png` | Sanitized screenshot/artifact folder showing output structure |

