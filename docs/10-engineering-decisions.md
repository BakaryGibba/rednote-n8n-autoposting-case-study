[Back to README](../README.md)

# 10 Engineering Decisions

## Decision Summary

The architecture favors safe, visible automation over fragile full autopublishing. The system uses APIs where available, RPA where necessary, and human confirmation where account risk or platform uncertainty is high.

## Key Trade-offs

| Decision | Trade-off | Outcome |
| --- | --- | --- |
| n8n orchestration | Less custom code, more workflow discipline | Faster iteration and visible operations |
| Google Sheets queue | Simple and accessible, less robust than a database | Useful lightweight control surface |
| Adapter routing | More branches, better platform fit | APIs and RPA can coexist safely |
| Attended RPA | Slower than stealth automation, safer for accounts | Login and security prompts remain human-owned |
| Mobile serialization | Lower throughput, higher stability | Avoids concurrent Appium/device conflicts |
| Human final review | Less hands-off, better compliance | Reduces accidental or risky publishing |

## Adapter Routing

```mermaid
flowchart TD
    Job[Approved publish job] --> Platform{Platform and mode}
    Platform --> Manual[Manual pack]
    Platform --> WebRPA[Attended web RPA]
    Platform --> MobileRPA[Mobile RPA]
    Platform --> DirectAPI[Direct API]
    Platform --> Partner[Approved partner tool]
    Manual --> Notify[Notify operator with assets and copy]
    WebRPA --> HumanReview[Fill form and stop for review]
    MobileRPA --> Device[Run serialized Android session]
    DirectAPI --> Publish[Publish through official API]
    Partner --> Publish
```

## Screenshot

![n8n multi-platform publishing workflow](../screenshots/n8n-overview.png)

The n8n canvas shows the adapter decision in practice: direct API platforms and RPA platforms run in separate lanes.
