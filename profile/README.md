# Chronos - packet scheduler

An Intent-Based Networking (IBN) system and adaptive L4 packet scheduler tailored for encrypted QUIC traffic streams in Kubernetes, powered by **eBPF/XDP**
## Overview

Chronos acts as a kernel-level Smart L4 Gateway (Load Balancer, Firewall, and QoS traffic shaper). It inspects unencrypted QUIC Connection IDs (CID) directly at the network driver layer without breaking end-to-end TLS encryption, translating high-level natural language intents into deterministic kernel rules.

## Organization Structure

* **[`intent-engine`](https://github.com/chronos-packet-scheduler/intent-engine)** — Intent Plane & Human-in-the-Loop UI; translates natural language into validated DSL instructions.
* **[`control-plane`](https://github.com/chronos-packet-scheduler/control-plane)** — Central Source of Truth; telemetry subscriptions, and state synchronization.
* **[`data-plane`](https://github.com/chronos-packet-scheduler/data-plane)** — Node-level eBPF/XDP agents executing CID-based routing, packet filtering, and traffic pacing inside the Linux kernel.
* **[`documentation`](https://github.com/chronos-packet-scheduler/documentation)** — Architecture specs, DSL schemas, and research notes.

## License

MIT
