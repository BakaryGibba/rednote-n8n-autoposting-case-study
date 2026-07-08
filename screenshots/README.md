[Back to README](../README.md)

# Screenshots Plan

Screenshots should be captured with sanitized demo data only. Do not include real account names, access tokens, n8n credential panels, private Drive files, browser profiles, cookies, downloaded real media, or platform session details.

## Capture List

| Status | File | What It Captures | Why It Matters |
| --- | --- | --- | --- |
| Captured | `n8n-overview.png` | Main combined RedNote/TikTok/IG/Facebook/LinkedIn workflow canvas | Shows orchestration complexity at a glance |
| Captured | `google-sheet-queue.png` | Queue sheet with demo rows and status columns | Shows the lightweight operations interface |
| Pending | `workflow-lane-routing.png` | n8n switch/router that separates direct API vs RPA lanes | Explains the adapter-based design |
| Captured | `rpa-service-terminal.png` | Local Node service running with safe logs only | Shows the bridge between n8n and automation |
| Captured | `appium-terminal.png` | Appium server running and Android device connected | Shows the mobile automation environment |
| Pending | `rednote-mobile-draft.png` | RedNote app draft/fill state using demo content | Shows attended mobile publishing |
| Pending | `tiktok-mobile-publish.png` | TikTok mobile automation state using demo content | Shows multi-platform mobile publishing |
| Pending | `status-sheet.png` | Status tab showing job result, message, and screenshot references | Shows operational traceability |
| Pending | `artifacts-folder.png` | Sanitized artifact/screenshot output folder | Shows recovery and review evidence |
| Pending | `runbook.png` | RPA runbook or safety checklist view | Shows safety-oriented operations |

## Capture Rules

- Use demo titles, captions, hashtags, and media.
- Hide n8n credential nodes and private environment values.
- Do not show real RedNote/TikTok account handles or phone numbers.
- Prefer screenshots of workflow structure over private execution logs.
- Crop or blur local file paths if they reveal private account information.
