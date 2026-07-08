[Back to README](../README.md)

# 04 n8n Workflow

## Workflow Summary

n8n is the orchestration layer. It reads approved queue rows, normalizes content and media, creates platform-specific lane items, calls the correct publishing adapter, merges results, and updates the original queue row.

## Combined Workflow

```mermaid
flowchart TD
    Trigger[Manual or Cron Trigger] --> Read[Read first ready queue row]
    Read --> Normalize[Normalize Drive link, title, caption, hashtags]
    Normalize --> Lanes[Create platform lane items]
    Lanes --> Switch{Publishing lane}
    Switch --> Direct[IG/Facebook/LinkedIn API branch]
    Switch --> RPA[RedNote/TikTok RPA branch]
    Direct --> Merge[Merge lane results]
    RPA --> Merge
    Merge --> Status{All platforms succeeded?}
    Status -->|Yes| Completed[Set status completed]
    Status -->|Some failed| Partial[Set status partially completed]
    Status -->|All failed| Failed[Set status failed]
    Completed --> Update[Update exact queue row]
    Partial --> Update
    Failed --> Update
```

## Workflow Design Choices

| Choice | Reason |
| --- | --- |
| Process first ready row only | Prevents one phone/Appium session from receiving concurrent jobs |
| Exact row update | Avoids overwriting the wrong content item |
| Per-platform status fields | Makes partial success visible |
| Direct API and RPA split | Uses the most stable lane available for each platform |

## Screenshot

![n8n multi-platform publishing workflow](../screenshots/n8n-overview.png)

The full workflow screenshot shows how a single queue row can fan out into direct API and RPA publishing lanes before merging status results.
