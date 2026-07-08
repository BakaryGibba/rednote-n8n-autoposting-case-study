[Back to README](../README.md)

# 01 Executive Summary

## Overview

RedNote Autoposting with n8n is an attended automation system for multi-platform content publishing. It coordinates Google Sheets, Google Drive, n8n workflows, a local Node.js RPA service, Playwright, Appium, and direct social APIs.

The project demonstrates practical automation engineering: workflow orchestration, adapter-based publishing, mobile RPA, human-in-the-loop safety, status synchronization, and operational runbooks.

## Product Narrative

Content teams often prepare the same post for several platforms, then manually download media, copy captions, open publishing interfaces, and update tracking sheets. This creates slow, repetitive work and inconsistent status visibility.

This project turns that process into a controlled queue:

| Step | System Responsibility |
| --- | --- |
| Queue | Read approved content from Google Sheets |
| Normalize | Prepare media, caption, hashtags, and platform fields |
| Route | Choose direct API or attended RPA lane |
| Publish | Execute through approved API, browser RPA, or mobile RPA |
| Sync | Write per-platform result back to the source row |

## Engineering Value

The case study is valuable because it shows how to build automation around unstable external platforms without pretending they are stable APIs. The design acknowledges platform limits, account safety, human review, and operational recovery.

## Screenshot

![n8n multi-platform publishing workflow](../screenshots/n8n-overview.png)

The n8n canvas shows the full publishing pipeline: queue intake, content normalization, platform lane routing, result merging, and row update.
