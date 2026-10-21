# Awesome-Photo-Video-Management

## Top Photo & Video Management Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Self-Hosted Backup, AI-Powered Discovery & Data Sovereignty*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Photo & Video Management**. These tools help you back up, organize, search, and share personal media libraries — from cloud services that sync automatically across devices to self-hosted platforms that keep every byte on hardware you control.

**Examples** include Immich, PhotoPrism, LibrePhotos, Ente, Nextcloud Memories, Google Photos, Apple iCloud Photos, Amazon Photos, Adobe Lightroom, and Mylio (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, local AI processing, and transparent data portability — ideal for privacy-conscious individuals and families who want Google Photos-level features without uploading their memories to someone else's cloud.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **[Google Photos](https://photos.google.com/)**  
  **The reference consumer photo service** with automatic backup, face grouping, semantic search, memories, and sharing. **15 GB free shared across Google services**; Google One plans from **$1.99/month for 100 GB** to **$9.99/month for 2 TB** . **Trade-offs**: **AI training on your photos** (opt-out available), **compression for "Storage saver" quality**, and **data portability is export-only** — you cannot mount or query your library programmatically . **Best for users prioritizing seamless cross-device sync and zero maintenance** over data control.

- **[Apple iCloud Photos](https://www.icloud.com/photos)**  
  **Apple's native photo sync** across iPhone, iPad, and Mac. **5 GB free**; plans from **$0.99/month for 50 GB** to **$9.99/month for 2 TB** . **Trade-offs**: **Apple ecosystem lock-in** — limited web access and no official API for programmatic library access . **Best for users fully committed to Apple devices** who value frictionless capture-to-sync.

- **[Amazon Photos](https://www.amazon.com/photos)**  
  **Unlimited full-resolution photo storage for Prime members**, with 5 GB for non-Prime and 5 GB for video. **Trade-offs**: **Interface and search lag behind Google Photos**; video storage is capped even for Prime . **Best for Prime members wanting free unlimited photo backup** as a secondary archive.

- **[Adobe Lightroom](https://lightroom.adobe.com/)**  
  **Professional photography workflow** with RAW processing, non-destructive edits, and cloud sync. **Plans from $9.99/month** (1 TB). **Trade-offs**: **Not a consumer backup service** — it's an editing tool with storage attached . **Best for photographers** needing professional RAW editing and catalog management.

- **[Mylio Photos](https://www.mylio.com/)**  
  **Local-first photo management with device sync** — photos stay on your devices and sync peer-to-peer. **Free tier** with paid plans for advanced features. **Best for users wanting multi-device access without cloud storage dependency** .

## Open-Source GitHub Projects

- **[Immich](https://github.com/immich-app/immich)**  
  **The closest open-source Google Photos replacement** — AGPL-3.0 licensed, **60,000+ GitHub stars**, extremely active development . **Native iOS and Android apps with automatic background backup** — the feature that sets it apart from every other self-hosted option . **Timeline view, face recognition, object detection, semantic search, maps, memories, shared albums, and partner sharing** — feature parity with Google Photos on most dimensions . **All AI runs locally** — face recognition, CLIP semantic search, and object detection via a dedicated machine-learning container . **Performance**: handles **250,000+ images** smoothly with GPU acceleration for indexing . **Security**: v2.10+ hardened with CSP, OIDC integration, and encryption at rest . **Deployment**: **6+ containers** (server, microservices, ML, PostgreSQL, Redis) via official Docker Compose — **requires 6 GB RAM minimum, 8 GB recommended**, with significant CPU/GPU for initial ML indexing . **Critical caveat**: **mobile upload into Immich is one copy, not a backup** — you must independently back up both the PostgreSQL database and the upload library . **Best for anyone wanting the closest Google Photos experience on their own hardware** — the default recommendation for self-hosted mobile-first backup [citation:1][citation:6][citation:13].

- **[PhotoPrism](https://github.com/photoprism/photoprism)**  
  **The most mature self-hosted photo manager for existing archives** — AGPL-3.0 licensed, **37,000+ GitHub stars** . **Excels at indexing and searching large libraries with camera originals, RAW files, videos, and extensive metadata** . **Powerful search filters** for browsing by color, subject, location, and metadata — the strongest search of the three major options . **RAW support and sidecar handling** are extensive . **AI features**: face recognition, object detection via TensorFlow, and automatic tagging . **Deployment**: **2 containers** (PhotoPrism + MariaDB) — the simplest of the major options, though with documented gotchas (database driver must be `mysql` even for MariaDB, dollar signs in passwords need escaping) . **RAM**: **500 MB-1 GB idle, 1-2 GB with ML** . **Trade-offs**: **no native mobile app** — PWA only, and the mobile experience is less polished than Immich . **No automatic phone backup** — requires a companion workflow like PhotoSync . **Best for photographers and archivists** with existing large libraries where metadata, RAW handling, and search depth matter more than phone-first backup [citation:1][citation:7][citation:13].

- **[LibrePhotos](https://github.com/LibrePhotos/librephotos)**  
  **The open-source AI discovery option** — MIT licensed, **7,000+ GitHub stars** . **Scans existing filesystem folders** and builds a timeline with **face recognition, scene detection, semantic image search, and event-based albums** ("Thursday in Berlin") . **Recent releases** added **photo stacks** (RAW+JPEG and Live Photos treated as one entity), **perceptual-hash duplicate detection**, **SigLIP 2 zero-shot tagging** (900+ real-world tags), **public album sharing with granular controls**, and **spotlight search** . **Local AI runs entirely on your infrastructure** — InsightFace/ArcFace-based face recognition and modern ML components . **Deployment**: **4+ containers** — moderate-to-high complexity, less documented than Immich or PhotoPrism . **RAM**: **8 GB+ recommended** for smooth ML workloads . **Trade-offs**: **no native mobile app** (PWA only), **mobile ecosystem less mature than Immich**, and **development slower than the leaders** . **Best for users prioritizing local AI and open-source control** over phone-first ecosystem [citation:1][citation:4][citation:7].

- **[Ente](https://github.com/ente-io/ente)**  
  **End-to-end encrypted photo backup** — **encryption keys never leave your device**, even Ente cannot see your photos. **Native mobile apps** with automatic backup. **Free tier** with paid plans. **Best for users wanting zero-knowledge encryption** without self-hosting — the privacy of self-hosting with the convenience of managed service.

- **[Nextcloud Memories](https://github.com/pulsejet/memories)**  
  **Photo management within Nextcloud** — **tight integration with your existing Nextcloud file storage and sharing** . **Timeline, albums, face recognition, and map view** . **Best for teams already running Nextcloud** wanting photo features without a separate service.

### Additional Strong Open-Source Options

- **Photoview** — Simple self-hosted photo gallery that scans existing folders. Lightweight alternative to Immich/PhotoPrism for browsing without AI overhead .
- **Piwigo** — Mature open-source photo gallery with albums, tags, and plugins. Web-based, self-hosted.
- **PhotoStructure** — Self-hosted photo organizer focused on deduplication and library consolidation.
- **ReFra** — Polished open-source Android gallery app with on-device AI categorization and a built-in image editor. Local-only, no server required .
- **Fx Fotos** — React Native open-source gallery app connecting to decentralized backends (Filecoin, Crust) .

**Frameworks for building custom systems**: Combine **Immich** for the closest Google Photos replacement with native mobile backup and local AI, **PhotoPrism** for mature archival and search of existing RAW-heavy libraries, **LibrePhotos** for local AI discovery with photo stacks and SigLIP 2 tagging, **Ente** for zero-knowledge encrypted backup without self-hosting, and **Nextcloud Memories** for photo management inside an existing Nextcloud deployment — to build a media management stack tailored to your backup workflow, library type, and privacy requirements.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Photo and video management tools differ significantly in backup model, AI capability, and operational complexity. **Immich is the closest Google Photos replacement** with native mobile apps and automatic background backup — but it requires 6+ containers, 6-8 GB RAM, and **mobile upload is not a backup on its own** . **PhotoPrism has the best search and RAW handling** for existing archives but no native mobile app or automatic phone backup . **LibrePhotos has strong local AI** (SigLIP 2, photo stacks, perceptual-hash dedup) but slower development and a rougher mobile experience . **Self-hosting shifts operational responsibility to you** — you must independently back up both the database and the media files; rescanning the library alone cannot reconstruct albums, users, shares, or face groups .
- Self-hosted open-source solutions require proper database backups (PostgreSQL dump for Immich, MariaDB for PhotoPrism), filesystem backups of the upload library, and monitoring of ML indexing resource usage.

---

**Made for privacy-conscious individuals, families, and photographers building photo and video libraries they own.**
Let's make photo and video management more open, self-hosted, and AI-capable.
