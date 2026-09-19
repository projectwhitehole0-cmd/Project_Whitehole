# Project Whitehole

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)
[![Architecture: Local--First](https://img.shields.io/badge/Architecture-Local--First-green.svg)](#the-sovereign-triad-architecture)
[![Consensus: Succinct_ZK](https://img.shields.io/badge/State-Recursive__SNARKs-purple.svg)](#whitehole-distributed-mesh--double-deduplication)
[![Security: Zero--Knowledge](https://img.shields.io/badge/Security-Zero--Knowledge-orange.svg)](#security--sovereignty-principles)

Project Whitehole is an open-source, sovereign spatial memory protocol designed for long-term personal digital archiving and 4D timeline reliving. 

By combining local-first zero-knowledge vaults, recursive zk-SNARK state consensus (Mina model), two-tier deduplication, and on-demand spatial generation, Project Whitehole allows individuals to archive, preserve, and navigate subjective temporal spaces without centralized corporate storage or telemetry.

---

## The Sovereign Triad Architecture

The protocol decouples local storage, distributed consensus, and spatial presentation across three distinct systems:


```

┌─────────────────────────────────────────────────────────────┐
│                   LOCAL USER DEVICE (MOBILE / PC)           │
│                                                             │
│   ┌─────────────────────────────────────────────────────┐   │
│   │ BLACKHOLE (Private Vault)                           │   │
│   │ • Local media, sensor logs & behavioral vectors     │   │
│   │ • Tier 1: Local Ingestion Deduplication (FFT/pHash) │   │
│   │ • Client-side ChaCha20-Poly1305 encryption          │   │
│   └──────────────────────────┬──────────────────────────┘   │
│                              │ State commitments (Hashes)   │
│                              ▼                              │
│   ┌─────────────────────────────────────────────────────┐   │
│   │ WHITEHOLE EMBEDDED NODE                             │   │
│   │ • Lightweight recursive zk-SNARK state verifier     │   │
│   │ • Local DAG branch reconciliation                   │   │
│   └──────────────────────────┬──────────────────────────┘   │
└──────────────────────────────┼──────────────────────────────┘
│ P2P Recursive SNARK Gossip
▼
┌─────────────────────────────────────────────────────────────┐
│           WHITEHOLE NETWORK (Shared Consensus Mesh)         │
│ • Distributed Directed Acyclic Graph (DAG) state            │
│ • Constant-size state proof (~22 KB, Mina architecture)     │
│ • Tier 2: Double Deduplication (Global spatial landmarks)   │
│ • Third-person consensus synthesis for deceased profiles    │
└──────────────────────────────┬──────────────────────────────┘
│ Synthesized Generative Slices
▼
┌─────────────────────────────────────────────────────────────┐
│ WORMHOLE (Independent Spatial Client Application)           │
│ • Connects ONLY to Whitehole (Zero access to raw Blackhole) │
│ • Lazy evaluation: on-demand 3D/4D timeline generation      │
│ • First-Person Perspective (FPP) OpenXR / WebXR rendering   │
│ • Local AI avatar embodiment & conversational visemes       │
└─────────────────────────────────────────────────────────────┘

```

---

## Core Systems & Mechanics

### 1. Blackhole: Sovereign Local Ingestion
The user's private repository for life telemetry, sensory logs, and decision vectors:
* **Tier 1 Deduplication (Local):** Employs Fast Fourier Transform (FFT) analysis and perceptual hashing (pHash) to prune duplicate camera bursts, near-identical frames, and redundant audio blocks locally before encryption.
* **Zero-Knowledge Encryption:** Payloads are sealed client-side via authenticated ciphers (ChaCha20-Poly1305). Private keys never leave the host hardware.
* **Behavioral Anchors:** Tracks the user's decision profiles across the six dimensions of personal wellness (Material, Relational, Abstract) to establish behavioral baseline vectors.

### 2. Whitehole: Distributed Mesh & Double Deduplication
The shared global consensus network reconciling temporal and spatial manifolds:
* **Succinct Recursive zk-SNARK State:** Built on recursive proof composition (similar to Mina Protocol's Pickles/Kimchi design). The entire network verification footprint compresses down to a constant-sized proof (~22 KB), enabling smartphones and edge devices to run embedded Whitehole nodes without memory exhaustion.
* **Tier 2 Deduplication (Double Deduplication):** Global spatial geometries, landmark point clouds, and public temporal anchors submitted across multiple vaults are deduplicated at the graph level into canonical anchors, preventing ledger bloating.
* **Collective & Deceased Synthesis:** Reconstructs historical events and deceased person profiles by intersecting overlapping third-person attestations without violating the privacy of individual participant vaults.
* **Probabilistic Possibility Manifolds:** Operates as a non-collapsing multigraph. Where records are sparse, it models multiple historical possibilities simultaneously, synthesizing plausible "dream state" spatial continuity rather than asserting rigid surveillance claims.

### 3. Wormhole: On-Demand Spatial Reliving
An independent client application dedicated to 3D/4D experiential navigation:
* **Strict Cryptographic Isolation:** Wormhole connects **only to Whitehole**. It has no direct access or decryption keys to any user's raw Blackhole vault, preventing interface-level data exfiltration.
* **Lazy Evaluation (Compute-on-Demand):** Spatial timelines, ambient audio, and avatars are generated strictly when a user requests to relive a temporal coordinate, minimizing idle power consumption.
* **First-Person Perspective (FPP):** Renders the user's viewpoint in WebXR/OpenXR, using local edge models for ambient voice synthesis and spatial embodiment.

---

## Repository Structure

```text
├── docs/                 # RFCs, recursive ZK circuits, and math models
├── core/
│   ├── blackhole/        # Local ciphers, FFT deduplication, and SQLite vault
│   ├── whitehole/
│   │   ├── node/         # Embedded mobile/edge light node
│   │   ├── snark/        # Recursive zk-SNARK prover and circuits
│   │   └── graph/        # Double-deduplicated DAG reconciliation engine
│   └── wormhole/         # OpenXR client, spatial runtime, and avatar pipeline
├── tests/                # Cryptographic invariants and determinism test suites
├── CONTRIBUTORS.md       # Community sponsors and core engineers
└── LICENSE               # GNU Affero General Public License v3

```

---

## Security & Sovereignty Guarantees

* **Air-Gapped Vault Security:** Blackhole data remains strictly local and encrypted. Only cryptographic commitments leave the device.
* **Strict Network Isolation:** Wormhole is architecturally sandboxed from Blackhole; it consumes synthesized graph states delivered by Whitehole.
* **Zero Corporate Telemetry:** Fully open source under the GNU AGPLv3, prohibiting proprietary SaaS enclosing and backdoors.

---

## Licensing & Contributions

Project Whitehole is published under the **GNU Affero General Public License v3 (GNU AGPLv3)**.

Any network deployment or modified service running this protocol must provide the corresponding source code to all network participants under identical terms.

**Maintainer:** Vishwas Singh

**Contact:** projectwhitehole0@gmail.com

```

```
