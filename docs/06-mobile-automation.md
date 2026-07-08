[Back to README](../README.md)

# 06 Mobile Automation

## Mobile Lane Summary

The mobile automation lane uses Appium and WebdriverIO to control an Android device or emulator. It exists because some publishing experiences are more stable or only accessible through mobile apps.

## Flow

```mermaid
sequenceDiagram
    participant n8n
    participant API as Local RPA API
    participant Appium
    participant Android as Android Device
    participant Platform as RedNote/TikTok App
    participant Sheet as Google Sheet

    n8n->>API: POST mobile publish job
    API->>Appium: Start serialized mobile session
    Appium->>Android: Launch target app
    Android->>Platform: Fill demo content and media
    Platform-->>Android: Draft or publish state
    Android-->>API: Result and screenshots
    API-->>n8n: Structured status
    n8n->>Sheet: Update platform status fields
```

## Safety Notes

- Mobile automation runs one job at a time.
- Login and security prompts are handled by the operator.
- Final publish can remain manual until the workflow is stable.
- Selector calibration is expected because mobile UI changes over time.

## Screenshot

![Appium Android automation terminal](../screenshots/appium-terminal.png)

The Appium runtime enables the Android publishing lane for mobile-first platform workflows.
