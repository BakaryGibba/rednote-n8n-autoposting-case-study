[Back to README](../README.md)

# 03 System Architecture

## Architecture Summary

The architecture separates orchestration from publishing adapters. n8n owns workflow coordination, while the local Node.js service exposes narrow RPA endpoints that can be called from workflow HTTP nodes.

```mermaid
flowchart LR
    subgraph Ops["Operations Layer"]
        Sheet[Google Sheets Queue]
        Drive[Google Drive Media]
        Operator[Human Operator]
    end

    subgraph Orchestration["n8n"]
        Trigger[Schedule or Manual Trigger]
        Normalize[Normalize Queue Row]
        Router[Publishing Lane Router]
        Sync[Status Sync]
    end

    subgraph RPA["Local RPA Service"]
        API[Express API]
        Validate[Zod Payload Validation]
        Web[Playwright Web Runner]
        Mobile[Appium Mobile Runner]
    end

    subgraph Platforms["Publishing Platforms"]
        RedNote[RedNote/Xiaohongshu]
        TikTok[TikTok]
        Meta[Instagram/Facebook APIs]
        LinkedIn[LinkedIn API]
    end

    Sheet --> Trigger
    Drive --> Normalize
    Trigger --> Normalize --> Router
    Router --> API
    Router --> Meta
    Router --> LinkedIn
    API --> Validate --> Web --> RedNote
    API --> Mobile --> RedNote
    API --> Mobile --> TikTok
    Web --> Operator
    Mobile --> Operator
    API --> Sync
    Meta --> Sync
    LinkedIn --> Sync
    Sync --> Sheet
```

## Component Responsibilities

| Component | Responsibility |
| --- | --- |
| Google Sheets | Queue, statuses, platform result messages |
| Google Drive | Source media files |
| n8n | Routing, scheduling, API calls, merge results, row updates |
| Node RPA service | Validates jobs and invokes browser/mobile automation |
| Playwright | Attended browser automation for web publishing |
| Appium/WebdriverIO | Android automation for RedNote and TikTok mobile apps |
| Operator | Handles login, CAPTCHA, 2FA, warnings, and final publish review |
