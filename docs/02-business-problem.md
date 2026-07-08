[Back to README](../README.md)

# 02 Business Problem

## Problem

Creators, agencies, and small marketing teams need to publish the same campaign across multiple channels. Manual posting is repetitive, slow, and easy to mis-track. Full automation is tempting, but social platforms introduce login challenges, UI changes, media constraints, and account safety concerns.

## Stakeholders

| Stakeholder | Need |
| --- | --- |
| Content operator | Prepare and publish posts without repetitive copy/paste work |
| Marketing lead | See which platforms succeeded, failed, or need attention |
| Automation engineer | Keep workflow logic maintainable and recoverable |
| Account owner | Avoid risky stealth automation and preserve account trust |

## Success Criteria

- One queue row can drive publishing across several platforms.
- Direct APIs handle platforms where supported.
- RPA handles platforms where API access is limited.
- Human intervention states are explicit and visible.
- Status updates return to the original row for operational tracking.

## User Journey

```mermaid
journey
    title Multi-platform Publishing Journey
    section Content Operator
      Adds approved row to Google Sheet: 5: Operator
      Attaches Drive media: 4: Operator
      Marks row ready: 5: Operator
    section Automation System
      Normalizes content and media: 4: n8n
      Routes platform lanes: 5: n8n
      Calls APIs or RPA service: 4: n8n
    section Human Review
      Confirms sensitive RPA publish states: 5: Operator
      Reviews final statuses: 5: Operator
```

## Screenshot

![Google Sheet publishing queue](../screenshots/google-sheet-queue.png)

The queue sheet demonstrates the lightweight operations interface used to coordinate multi-platform publishing.
