# NVIDIA — Senior Software Engineer, Object Storage - DGX Cloud

- **Posting:** https://nvidia.wd5.myworkdayjobs.com/NVIDIAExternalCareerSite/job/US-CA-Santa-Clara/Senior-Software-Engineer--Object-Storage---DGX-Cloud_JR2025155
- **Req ID:** JR2025155
- **Location:** US-CA-Santa Clara
- **Collected:** 2026-10-02
- **Apply by:** at least until October 2, 2026 (per posting — urgent)
- **Vacancy type:** existing vacancy (not pipeline)

## Compensation

- Level 4 base: $184,000 – $287,500
- Level 5 base: $224,000 – $356,500
- Plus equity and benefits

## Role summary

Design, implement, and extend NVIDIA's **internal object storage system** — a core
service for NVIDIA AI/ML research teams building generative AI systems and world
models. Stated scale: **10k+ nodes, exabytes of data**.

### What you will be doing

- Design, development, and testing of the object storage system
- Storage capabilities for NVIDIA research teams and other users
- Availability and reliability at scale (10k+ nodes, exabytes)
- System performance analysis and improvement at all levels
- End-to-end automation: provisioning, management, monitoring
- Upstream contributions to open source storage codebases

### What they need to see

- Track record developing object storage services; strategies for data
  availability, durability, fault tolerance
- History of product ownership from inception to support
- Communication and presentation skills
- Distributed systems experience in Python, Go, C/C++, or similar
- BS in CS or related field (or equivalent experience)
- 8+ years relevant experience

### Ways to stand out

- Developed/delivered major components of a distributed storage system at
  exabyte scale
- Concurrency models and primitives (threads, event loops, distributed locking)
- Built/delivered cloud storage/data services; sustained open source contributions

## Key signals

1. **Internal system, not a product** — users are NVIDIA's own research teams;
   reliability directly gates AI research velocity.
2. **Open source footprint matters** — "contributions upstream to open source
   storage codebases" suggests the system is built on / deeply integrated with
   open source storage; sustained OSS contributions are an explicit stand-out.
3. **AI-infra storage angle** — checkpointing at scale, training data loading
   (GPU-direct storage, Magnum IO ecosystem) differentiates this from generic
   object storage roles.

## Interview prep topics

1. Object storage internals: erasure coding vs replication tradeoffs, placement
   algorithms (consistent hashing / CRUSH-like), S3 consistency semantics
2. Durability math: nines, MTTDL, failure domains, rebuild storms
3. Concurrency: lock-free structures, event-loop architectures (Seastar-style),
   distributed coordination (Raft / etcd)
4. Performance: tail latency, IO path optimization, SPDK / RDMA / kernel bypass
5. AI workload storage: high-frequency checkpointing, large-scale training data
   ingest, GPU-direct paths
6. Behavioral: end-to-end ownership story (inception → support) with a
   reliability incident at scale; cross-team work with research users
