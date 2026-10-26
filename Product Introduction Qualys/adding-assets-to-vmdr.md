# Merge Data for a Single Unified View

## Overview

There are multiple ways to scan an asset: authenticated scans, unauthenticated scans, and Cloud Agent scans.

It is important that all vulnerability detections link back to the same asset, even if the key identifiers for the asset, like IP address or hostname, have changed over its lifecycle.

It is essential that **Unified Vulnerability View** is enabled so that detections are merged into a single asset record.

## Key Concepts

### 1. Tracking Methods

When adding scannable hosts to the subscription, you choose an IP, DNS, or NetBIOS tracking method.

### 2. Qualys Host ID

Cloud Agent findings are tracked by a UUID called the **Qualys Host ID** that gets written on the host asset.

### 3. Agentless Tracking

Agentless Tracking provides scannable hosts with the same Qualys Host ID that the Cloud Agent uses.

### 4. Correlation Identifier

The Correlation Identifier also provides a unique identifier, published by the Cloud Agent, and is used to merge Cloud Agent scans with unauthenticated (“Remote Only”) scans.

### 5. Unified View

Unified View refers to a single record for the asset that includes both scan and agent data.

## Key Takeaways

- Multiple scan methods include authenticated scans, unauthenticated scans, and Cloud Agent scans.
- All vulnerability detections should link back to the same asset, even if its IP address or hostname changes.
- Unified Vulnerability View enables detections to be merged into a single asset record.
- The Qualys Host ID is a UUID used to track Cloud Agent findings.
- Agentless Tracking provides scannable hosts with the same Qualys Host ID that the Cloud Agent uses.
- The Correlation Identifier is used to merge Cloud Agent scans with unauthenticated (“Remote Only”) scans.
- Unified View combines scan and agent data into a single asset record.

## Key Application

Enable Unified Vulnerability View to ensure that vulnerability detections from different scanning methods are merged into a single asset record, even when key asset identifiers change over time.
