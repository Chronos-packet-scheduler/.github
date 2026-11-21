# Chronos

An Intent-Based Networking (IBN) system and adaptive L4 packet scheduler tailored for encrypted QUIC traffic streams in Kubernetes, powered by **eBPF/XDP**

## Overview

Chronos acts as a kernel-level Smart L4 Gateway (Load Balancer, Firewall, and QoS traffic shaper). It inspects unencrypted QUIC Connection IDs (CID) directly at the network driver layer without breaking end-to-end TLS encryption, translating high-level natural language intents into deterministic kernel rules.

## Organization Structure

* **[`intent-engine-backend`](https://github.com/chronos-packet-scheduler/intent-engine-backend)** - Intent Plane (Python); translates natural language into validated DSL instructions.
* **[`intent-engine-frontend`](https://github.com/chronos-packet-scheduler/intent-engine-frontend)** - Human-in-the-Loop operator UI (Next.js).
* **[`control-plane`](https://github.com/chronos-packet-scheduler/control-plane)** - Central Source of Truth (Go); telemetry subscriptions, and state synchronization.
* **[`data-plane`](https://github.com/chronos-packet-scheduler/data-plane)** - Node-level eBPF/XDP programs (C) and agent (Rust) executing CID-based routing, packet filtering, and traffic pacing inside the Linux kernel.
* **[`deploy`](https://github.com/chronos-packet-scheduler/deploy)** - Docker Compose and Kubernetes manifests to run the whole system.
* **[`documentation`](https://github.com/chronos-packet-scheduler/documentation)** - Architecture specs, DSL schemas, and research notes.

## Quickstart

Every service is published to `ghcr.io/chronos-packet-scheduler/<repo>`. To run everything locally (e.g. on Rancher Desktop), see [`deploy`](https://github.com/chronos-packet-scheduler/deploy).

## License

MIT
