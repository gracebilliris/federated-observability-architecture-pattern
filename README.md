# Federated Observability Architecture Pattern for Reliable Agentic AI Software Systems
This demonstration showcases a telemetry pipeline built with **n8n**, an open-source workflow automation platform. It illustrates how heterogeneous data can be ingested, normalised, and monitored with minimal coding.

## Overview

The workflow is divided into two main parts:

### 1. Ingestion Workflow
- **Input:** Sample telemetry events from multiple external systems, each with different schemas.
- **Process:**
  - Events are ingested into a raw **MongoDB** collection with timestamps for traceability.
  - Events are then published to a **Kafka** topic, providing a staging layer for reliability and back-pressure.
  
### 2. Consumption & Normalisation Workflow
- **Trigger:** Kafka messages initiate the workflow via a Kafka Trigger node.
- **Process:**
  - Events are transformed and normalised using a simple AI model (Google’s Gemini) to standardise fields, types, and enrich data.
  - Normalised events are inserted into the telemetry database.
  - Metrics for successful transformations, errors, and latency are calculated and sent to **Grafana Loki** for observability.

## Purpose
This demo illustrates the feasibility of a **Federated Observability Architecture Pattern** in a **proof-of-concept** prototype, showing that heterogeneous telemetry can be processed, normalised, and monitored in a traceable, reliable workflow.

## Demonstration Video 
For more details, watch the [demonstration video](https://www.youtube.com/watch?v=uWY3sr18-9g&feature=youtu.be).

Note: it is a feasbility prototype.