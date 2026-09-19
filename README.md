# Project Whitehole

Project Whitehole is a sovereign, local-first protocol and indexing engine designed for long-term personal digital preservation and 4D spatial timeline reconstruction.

By combining deterministic event-graph structures, zero-knowledge local encryption, and reproducible spatial pipelines, Project Whitehole enables individuals to archive media, personal logs, and environmental telemetry on their own hardware without platform lock-in, proprietary cloud dependencies, or corporate telemetry.

---

## The Sovereign Triad Architecture

Project Whitehole partitions spatial memory preservation into three decoupled, mathematically verifiable systems:

* **Blackhole (Cryptographic Storage & Ingestion):**
The localized zero-knowledge data vault. Raw artifacts (photos, video, audio, sensor streams) are ingested locally, deduplicated using Fast Fourier Transform (FFT) frequency analysis, and locked under authenticated client-side encryption (ChaCha20-Poly1305 / AES-256-GCM). Data remains cryptographically sealed against external observation.
* **Whitehole (Deterministic Graph Sequencing):**
The central timeline and narrative engine. It translates encrypted event streams into an append-only, content-addressed Directed Acyclic Graph (DAG). Keyframes and spatial coordinates are interpolated deterministically across multi-source sensor inputs without proprietary cloud dependencies.
* **Wormhole (Spatial Interface & Navigation):**
The interactive presentation layer built on open spatial computing standards (OpenXR, WebXR). It projects deterministic timeline graphs into explorable 3D/4D environments, allowing users to navigate preserved temporal spaces locally in real time.

```
[ Raw Personal Media, Sensor Streams & Telemetry ]
                        │
                        ▼
┌─────────────────────────────────────────────────────────────┐
│ BLACKHOLE  (Zero-Knowledge Ingestion & Local Storage)       │
│ • FFT frequency analysis & perceptual deduplication         │
│ • Client-side authenticated encryption (ChaCha20-Poly1305)  │
│ • Air-gapped key management & local content-addressing      │
└──────────────────────────────┬──────────────────────────────┘
                               │ Authenticated Keyframes & Payloads
                               ▼
┌─────────────────────────────────────────────────────────────┐
│ WHITEHOLE  (Deterministic Graph Engine & Core Protocol)     │
│ • Immutable Directed Acyclic Graph (DAG) state logging      │
│ • Multi-source sensor alignment & timestamp consensus       │
│ • Deterministic mathematical spatial interpolation          │
└──────────────────────────────┬──────────────────────────────┘
                               │ Spatial Trajectories & Event Nodes
                               ▼
┌─────────────────────────────────────────────────────────────┐
│ WORMHOLE   (Spatial Interface & Client Navigation)          │
│ • OpenXR, WebXR, and glTF runtime integration               │
│ • Local real-time 3D/4D timeline reconstruction             │
│ • Zero-telemetry, client-only spatial rendering             │
└─────────────────────────────────────────────────────────────┘

```

---

## Engineering Pipeline

### 1. Blackhole: Cryptographic Ingestion & Invariant Deduplication

Raw media and temporal inputs are processed locally through an immutable, content-addressed pipeline:

* **Perceptual & Spectral Deduplication:** Fast Fourier Transform (FFT) analysis and perceptual hashing isolate redundant frames and media blocks before indexing, preserving disk bandwidth.
* **Client-Side Authenticated Encryption:** Payload blocks are encrypted prior to persistence using authenticated ciphers (ChaCha20-Poly1305). Encryption keys remain exclusively on the user's host machine. Plaintext data never traverses external boundaries.

### 2. Whitehole: Deterministic Timeline Engine

Temporal events are resolved as an append-only Directed Acyclic Graph (DAG):

* **Immutable Anchors:** Cryptographically verified timestamps establish immutable parent-child references.
* **Deterministic Interpolation:** Spatial trajectories and continuous event streams reconcile across multi-source logs using deterministic geometric transforms, eliminating arbitrary hallucinations and dependencies on third-party cloud servers.

### 3. Wormhole: Open Spatial Interface

* **Open Protocols:** Built natively against OpenXR, WebXR, and standard glTF scene representations.
* **Hardware Independence:** Runs entirely on standard consumer workstations, edge compute nodes, and local storage arrays without requiring proprietary cloud environments or closed hardware platforms.

---

## Security & Sovereignty Principles

* **Zero Cloud Telemetry:** No analytics endpoints, tracking beacons, or telemetry sinks are bundled or executed.
* **Air-Gapped Operation:** Ingestion, indexing, graph resolution, and spatial traversal operate in completely offline, air-gapped environments.
* **Cryptographic Isolation:** Cross-device synchronization functions strictly over mutually authenticated, encrypted peer-to-peer tunnels (such as local LAN, direct libp2p channels, or onion routing) requiring explicit physical pairing.

---

## Repository Structure

```text
├── docs/                 # Protocol specifications, RFCs, and mathematical models
├── core/
│   ├── blackhole/        # Local ciphers, key derivation, and FFT deduplication
│   ├── whitehole/        # Deterministic DAG timeline sequencing engine
│   └── wormhole/         # OpenXR/WebXR spatial interfaces and client renderer
├── tests/                # Cryptographic invariants and determinism test suites
├── CONTRIBUTORS.md       # Founding members, sponsors, and core engineers
└── LICENSE               # GNU Affero General Public License v3

```

---

## Research & Documentation

* **Engineering Dispatches:** Long-form architectural breakdowns, mathematical proofs, and progress notes are published regularly on our Substack.
* **Specifications:** Detailed protocol RFCs covering data schemas, deterministic reconciliation, and spatial pipeline specifications are maintained directly in the `/docs` directory.

---

## Licensing & Contributions

Project Whitehole is distributed under the **GNU Affero General Public License v3 (GNU AGPLv3)**.

The AGPLv3 preserves software sovereignty and guarantees reciprocal distribution. Any network-accessible implementation or derivative service deploying this engine must make the complete corresponding source code available under identical licensing terms.

### Contributing

We welcome contributions from engineers focused on:

* Content-addressed storage, deduplication, and distributed DAG synchronization
* Local-first zero-knowledge cryptography and key derivation
* OpenXR, computational geometry, and real-time 3D/4D rendering pipelines

Review our contribution guidelines and pull request template before submitting architectural changes.

**Maintainer:** Vishwas Singh

**Contact:** projectwhitehole0@gmail.com
