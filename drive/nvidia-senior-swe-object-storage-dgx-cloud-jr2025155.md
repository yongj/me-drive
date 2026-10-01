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
