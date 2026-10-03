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
2. **Object storage scalability (JD: 10k+ nodes, exabytes —着重)**: metadata
   scaling (centralized vs partitioned vs fully distributed), placement and
   rebalancing at exabyte scale, failure-domain-aware layout, rebuild traffic
   vs foreground IO under massive node counts, small-object problem, scaling
   the control plane (placement/membership/heartbeat) independently of the
   data plane
3. Durability math: nines, MTTDL, failure domains, rebuild storms
4. Concurrency: lock-free structures, event-loop architectures (Seastar-style),
   distributed coordination (Raft / etcd)
5. Performance: tail latency, IO path optimization, SPDK / RDMA / kernel bypass
6. AI workload storage: high-frequency checkpointing, large-scale training data
   ingest, GPU-direct paths
7. **KV cache / quantization (priority raised 2026-10-03)**: KV cache is
   storage-adjacent (large, write-heavy, latency-sensitive state for inference)
   and a hot topic — user discussed it with an NVIDIA contact on 2026-10-03.
   Prep: KV cache layout and memory hierarchy (HBM → host → SSD tiering),
   prefix caching / sharing, eviction and recompute tradeoffs, quantization
   of KV cache (INT8/FP8, per-token vs per-channel scales), interplay with
   paged attention
8. Behavioral: end-to-end ownership story (inception → support) with a
   reliability incident at scale; cross-team work with research users

## 1point3acres NVIDIA question bank (collected 2026-10-03)

- Source: https://www.1point3acres.com/interview/problems/company/nvidia
  (71 questions total, 50 coding; free preview shows 21, ~19 unique after
  dedupe). Official intro: NVIDIA interviews are highly team-specific and far
  less LeetCode-bank-driven than other large tech loops; System Software /
  Linux / Tegra / DGX AI infra / Deep Learning roles lean toward engineering
  scenarios (C/C++ debugging, graph validation, GPU/inference fundamentals,
  small utility coding, project deep dives).
- GPU/inference engineering: FP32 tensor → INT8 quantization (asymmetric
  quantization follow-ups: zero point, how scale/zero-point shift under
  non-symmetric distributions, numerical stability; appears twice); implement
  a decoder KV cache.
- C/C++ fundamentals: reference-counted smart pointer from scratch; C++
  debugging and output prediction (pointers, inheritance, multithreading);
  2D matrix transpose in C++ with memory/cache trade-off discussion.
- Engineering-scenario coding (most NVIDIA-flavored): merge two sorted files
  with bounded memory (appears twice); graph API insert/configure/validate
  with cycle detection and structural constraints; computation graph pruning
  to keep the optimal path; simulation-style coding with scaling follow-up
  (mini system design); Python data processing (parse, aggregate, validate);
  Linux shell text/log processing; aggregate logs by status code (count and
  average latency); integrate a public GET API and transform results; OOP
  key-value store (set/get/setAll); SQL aggregation across
  country/state/city/zip tables.
- Classic algorithms: Top K frequent elements in a data stream; Reaching
  Points; longest/count substrings without repeating characters (appears
  twice); Merge Intervals; Count Visible Towers; Excel-style string
  compress/decompress; find any duplicate in [1, n-1] with O(1) extra space;
  N×N matrix row/column swap transform; N-th prime; encode/decode string
  list; validate parentheses; tree planting on a grid (no adjacent trees).
- Implication for this role: the bank confirms the "engineering over
  LeetCode" pattern — prioritize C++ fundamentals, engineering-scenario
  coding (large-file merge, KV store, log processing), and distributed
  system design (thin in the bank; cover via interview writeups instead).
  Quantization/KV cache items are inference-leaning but worth prepping given
  the storage-adjacent angle and current heat (see prep topic 7).

## Related interview experiences (collected 2026-10-02)

Searched 1point3acres via external search engine (site: queries — in-site
search not used to avoid spending forum currency) plus Blind and LeetCode CN.
No complete onsite (VO) writeup was found for an NVIDIA object-storage /
distributed-storage team; storage-specific loops are scarce. What exists
clusters around DGX Cloud / AI infra.

### Strongly relevant (storage / distributed / infra)

- [急需米,发一个核弹厂的面筋](https://www.1point3acres.com/bbs/thread-1138229-1-1.html)
  (2025-07-24) — DGX Cloud deeplearning software intern phone screen, all
  distributed systems design: multi-user counter locking; artifact store on
  K8s + Cassandra cluster (how artifacts are stored, data structures for
  concurrent creates, delete-then-add semantics, read API optimization).
- [女大 dgx ai infra eng 店面](https://www.1point3acres.com/bbs/thread-1160173-1-1.html)
  (2026-01-06) — DGX AI infra phone screen: new cloud account cluster bring-up,
  first k8s deploy, VM internals, CI/CD image build/upload/pull, concurrency,
  k8s operators & CRDs; coding: log parser counting items + top N.
- [NVIDIA System Software Engineer 面试咋准备](https://www.1point3acres.com/bbs/thread-1023836-1-1.html)
  (2023-10-25) — NVIDIA Cloud Storage group intern prep: JD asked for hands-on
  coding (Golang/Python preferred) and familiarity with S3-class cloud storage
  tech; process starts with team match, first round possibly hiring manager.
- [Anyone Interviewed for NVIDIA Storage Management Platform (DGX Cloud)?](https://www.teamblind.com/post/anyone-interviewed-for-nvidia-storage-management-platform-dgx-cloud-y218blqa)
  (2026-05-30, Blind) — Senior Full-Stack SWE, Storage Management Platform
  (DGX Cloud); top reply: spend 30+ minutes studying NVIDIA-specific k8s
  tooling and hardware characteristics.

### General NVIDIA SWE reference

- [NVIDIA面经汇总：8篇帖子/资料+68道题库题](https://www.1point3acres.com/bbs/thread-1190285-1-1.html)
  (2026-09-22) — consensus: slow process, team-specific interview style,
  C++ dominant.
- [Nvidia deeplearning software engineer](https://www.1point3acres.com/bbs/thread-1168121-1-1.html)
  (2026-03-12) — phone screen: 4 C++ find-the-bug + predict-output questions
  (pointers, inheritance, multithreading), no intro, no resume walkthrough.
- [显卡厂DGX ai infra security engineer 电话一轮游](https://www.1point3acres.com/bbs/thread-1138966-1-1.html)
  (2025-07-29) — resume + BQ + coding, one round rejection; rounds vary by team.
- [核弹店面刮净](https://www.1point3acres.com/bbs/thread-1146977-1-1.html)
  (2025-09-23) — DGX Cloud phone screen (HM swapped for SDE): fizzbuzz +
  follow-up on passing maps, 30 min, "not a match".
- [NVIDIA Software Cloud/Infrastructure HackerRank Challenge](https://www.1point3acres.com/bbs/thread-935082-1-1.html)
  (2022-10-09) — campus OA: 25 min, 1 question.

### Observed pattern

Interviews are highly team-specific; phone screens often run by the hiring
manager or a team SDE directly. Three recurring blocks: infra/systems knowledge
(K8s deploys, operators/CRDs, VM internals, CI/CD, concurrency), distributed
systems design (locking, artifact store semantics), and C++ fundamentals
(find-the-bug / predict-output on pointers, inheritance, threads). Coding is
lighter and engineering-flavored (log parsing, top-N) rather than pure
algorithm puzzles. Glassdoor's NVIDIA storage interview page was blocked by
Cloudflare bot protection and could not be read; LeetCode CN had no
NVIDIA-storage-specific writeups.

## Background research: NVIDIA storage engineering (collected 2026-10-02)

Note: NVIDIA has not publicly documented the internal object storage system
itself (the JD describes an internal system: 10k+ nodes, exabytes, serving
AI/ML research teams). The materials below cover the surrounding stack.

### NVIDIA Technical Blog (developer.nvidia.com)

- GPUDirect tag archive: https://developer.nvidia.com/blog/tag/gpudirect/
- "ModelExpress: Distributing Model Artifacts at the Speed of Light"
  (2026-07-24) — distributing model checkpoints (hundreds of GB to TB) at
  speed; directly relevant to object storage for AI artifacts.
- "Cut Checkpoint Costs with About 30 Lines of Python and NVIDIA nvCOMP"
  (2026-04-09) — LLM checkpoint save/resume cost optimization.
- "Accelerating AI Storage by up to 48% with NVIDIA Spectrum-X Networking
  Platform and Partners" (2025-02-04) — storage fabric for AI factories.

### Research paper

- FMS 2025 paper "Advancing Memory and Storage Architectures for Next-Gen AI
  Workloads" — introduces SCADA (Scaled Accelerated Data Access): GPUs
  initiate and control storage IO directly, taking the control path off the
  CPU (GPUDirect had only offloaded the data path). Summary:
  https://www.blocksandfiles.com/ai-ml/2025/11/25/nvidia-scada-offloads-storage-control-path-to-the-gpu/1711995

### Official docs / primers

- NVIDIA GPUDirect Storage and Magnum IO documentation (docs.nvidia.com) —
  the official answer to "performance at all levels" in the JD.
- BeeGFS + GPUDirect Storage explainer (good GDS technical background):
  https://www.beegfs.io/c/beegfs-now-supports-nvidia-magnum-io-gpu/

### Ecosystem context

- NVIDIA Eos supercomputer (4,608 H100) uses DDN EXAScaler: 48 AI400NVX2
  appliances, 12 PB flash, 4.3 TB/s read, 3.1 TB/s write — NVIDIA's own
  research clusters historically ran external parallel filesystems, so the
  internal object storage in the JD is likely a newer DGX Cloud-era project.
  Source: https://per3s.github.io/per3s.2024/material/2024_per3s_NCP_storage_architecture.pdf
- NVIDIA-Certified Storage program (GTC 2026): Cloudian HyperStore 8.2.6
  (S3-compatible, exabyte-scalable) certified — S3 API is the standard
  interface for NVIDIA-validated AI storage.
  Source: https://www.storagenewsletter.com/2026/03/18/nvidia-gtc-2026-cloudian-hyperstore-achieves-nvidia-certified-storage-designation/
- MinIO AIStor on NVIDIA STX / BlueField DPUs with GPUDirect RDMA for
  S3-compatible storage (tech preview) — object storage moving from capacity
  tier to performance tier.
  Source: https://www.storagenewsletter.com/2026/03/17/nvidia-gtc-2026-minio-aistor-brings-object-data-stores-for-the-nvidia-stx-reference-architecture/
- NVIDIA Dynamo NIXL supports Amazon S3 for KV cache offload (GTC 2025) —
  object storage entering the inference path.

### Interview implication

Since the internal system is not public, expect generic object storage design
depth (S3 semantics, erasure coding, placement, consistency) plus NVIDIA
flavor (GDS, checkpointing, AI workload IO patterns).
