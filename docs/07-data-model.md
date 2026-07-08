[Back to README](../README.md)

# 07 Data Model

## Data Model Summary

The project models accounts, content items, assets, publish jobs, and publish attempt logs. Google Sheets can act as a lightweight operational surface, while a database-backed model provides the path toward production reliability.

## ER Diagram

```mermaid
erDiagram
    BRAND_ACCOUNT ||--o{ CONTENT_ITEM : owns
    CONTENT_ITEM ||--o{ CONTENT_ASSET : has
    CONTENT_ITEM ||--o{ PUBLISH_JOB : creates
    PUBLISH_JOB ||--o{ PUBLISH_ATTEMPT_LOG : records

    BRAND_ACCOUNT {
        uuid id
        uuid client_id
        string platform
        string account_name
        string posting_mode
        boolean require_human_approval
        boolean allow_auto_publish
        string status
    }

    CONTENT_ITEM {
        uuid id
        uuid client_id
        string platform
        string post_type
        string title
        string approval_status
        string status
        datetime scheduled_at
    }

    CONTENT_ASSET {
        uuid id
        uuid content_item_id
        string asset_type
        string file_url
        string local_path
        int sort_order
        boolean is_cover
    }

    PUBLISH_JOB {
        uuid id
        uuid content_item_id
        string platform
        string adapter_type
        string status
        int attempt_count
    }

    PUBLISH_ATTEMPT_LOG {
        uuid id
        uuid publish_job_id
        string step_name
        string step_status
        string screenshot_url
    }
```

## Status Concepts

| Status Area | Purpose |
| --- | --- |
| Content status | Tracks draft, scheduled, completed, partially completed, or failed workflow state |
| Approval status | Separates content approval from publishing execution |
| Publish job status | Tracks adapter execution outcome |
| Attempt logs | Captures step-level traceability and screenshots |

## Screenshot Placeholder

**File:** `screenshots/status-sheet.png`

Capture the status sheet with demo results and no real platform account information.

