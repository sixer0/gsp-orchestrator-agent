# Global Memory Index

## Current Projects
- **Project:** Library CLI (dkatalis-test)
- **Path:** E:\Projects\dkatalis-test
- **Stack:** Node.js + TypeScript + tsx (no build step)
- **Phase:** Final report committed and private archive refreshed; local-only/no push
- **Task folder:** `docs/2026_06_18_solve_problem_nodejs_typescript/`
- **Key decision:** Waitlist fulfillment corrected 2026-06-18 — return transfers book to first waitlisted user (book stays borrowed), stores notification, shifts positions. NOT notification-only.

## Current Project (2026-06-12)
- **Project:** Comprehensive E-commerce App
- **Path:** E:\Projects\e-commerse
- **Stack:** NestJS + Next.js 15 + Prisma + SQLite + Radix UI + Tailwind v4
- **Phase:** Phase 2 COMPLETE | Phase 3 PENDING

## Current Project: ARSENAL IDS (2026-07-15)
- **Project:** ARSENAL Intrusion Detection System — TNI AL
- **Path:** `/Users/mbp/Documents/Project/ARSENAL/`
- **Kontraktor:** PT Gemilang Satria Perkasa (GSP)
- **Partner:** Heimdal Defence Pte Ltd (Singapore)
- **Phase:** R1-R4 COMPLETE | R5 COMPLETE (17 Jul 2026) | R6-R7 PLANNED
- **Top-level Index:** `docs/README.md` (mulai dari sini)
- **Knowledge Base:** `docs/2026-07-15_arsenal_product_knowledge_compilation/`
- **Alternative Research:** `docs/2026-07-15_arsenal_product_alternative_research/`
- **Deep Reference:** `memory/refs/arsenal-product-research.md`
- **R5 Architecture:** `memory/refs/arsenal-r5-system-integration.md`
- **Next Plan:** `nextplan.md` (updated post-R5)
- **Key Metrics:** 22 produk, Rp 38-46B revised budget, 11 dims architecture, CONDITIONAL GO
- **CRITICAL FINDINGS (R5 System Integration):**
  - **CONDITIONAL GO** — 87/87 AC PASS, 45/45 consistency pairs
  - **Total system power:** 11,831W typ / 25,802W max (83.9% headroom)
  - **Total cable:** 29,977m (187% of 16,000m baseline)
  - **Bandwidth:** 5,735 Mbps aggregate, 0 bottlenecks
  - **LOCAL-FIRST 87%** — Verihubs 0% critical dependency
  - **5-level data sovereignty** — 3 air-gapped segments, 12 cloud controls
  - **ONVIF/REST/SNMP abstraction** — vendor lock-in LOW
  - **Installation:** 174-214 days, NRE $50K-100K
  - **P22 SDPPI = DEAL-BREAKER** — Rp 50-150M, 8-10 weeks
  - **Hidden costs revealed:** 61× encoder boards + 61× DC PSU for P11
  - Deep Reference: `memory/refs/arsenal-r5-system-integration.md`
- **CRITICAL FINDINGS (Riset 2):**
  - OEM Direct Procurement: **Rp 32.6 Miliar savings** (8 produk markup tinggi)
  - TKDN: 5/22 native (22.7%) → roadmap 90.9% dalam 5 tahun
  - UU PDP: 4 produk biometrik (P13/P15/P16/P18) compliance gaps
  - P21 Sentinel: SPECS BLACKOUT — CAUTION gate, minta datasheet
  - P20: Base chassis only warning (Rp 43.7J tanpa I/O boards)
  - 6 produk EOL: Semua sudah punya current-gen replacement
- **R3 KEY FINDINGS (Component Decomposition):**
  - ~270 komponen terdekomposisi: 98 local (36.3%), 119 import (44.1%), 53 hybrid (19.6%)
  - TKDN 17/22 (77.3%) compliant via 3-track model (naik dari 22.7% baseline)
  - Standardisasi 3 vendor: Supreme Cable + Indorack + ARSA = 92% produk
  - Penghematan Rp 10.6-17.2B total (standardization + Heimdal bypass + HDD avoidance)
  - 4 produk UU PDP non-compliant (P13/P15/P16/P18)
  - 40+ HS codes identified, >85% BM 0% via ITA
  - Deep Reference: `memory/refs/arsenal-r3-component-vendor.md`
- **STATUS:** R1-R5 COMPLETE — siap R6 (TCO) + R7 (Competitive). P22 SDPPI harus dimulai SEKARANG.
- **Next:** R6 TCO (full data dari R5), R7 Competitive (3-layer differentiator), P22 SDPPI type-approval (8-10 weeks)

## Task Reports

| Date | Task | Status | Path |
|------|------|--------|------|
| 2026-07-16 | [Orchestration Issue Analysis](memory/tasks/2026-07-16-orchestration-issue-analysis.md) | COMPLETE | `docs/2026_07_16_orchestration_issue_analysis/` |
| 2026-07-16 | [ARSENAL Product Alternative Research](memory/tasks/2026-07-16-arsenal-product-alternative-research.md) | COMPLETE | `docs/2026-07-15_arsenal_product_alternative_research/` |
| 2026-07-16 | [ARSENAL Component & Vendor Research](memory/tasks/2026-07-16-arsenal-component-vendor-research.md) | COMPLETE | `docs/2026-07-16_arsenal_component_vendor_research/` |
| 2026-07-17 | [ARSENAL R5 System Integration](memory/tasks/2026-07-16-arsenal-r5-system-integration.md) | COMPLETE | `docs/2026-07-16_arsenal_r5_system_integration/` |
| 2026-07-15 | [ARSENAL Product Knowledge Base](memory/tasks/2026-07-15-arsenal-product-knowledge.md) | COMPLETE | `docs/2026-07-15_arsenal_product_knowledge_compilation/` |
| 2026-07-09 | [Comprehensive Research Flow](memory/tasks/2026-07-09-comprehensive-research-flow.md) | COMPLETE | — |
| 2026-06-12 | [E-commerce Phase 2](memory/tasks/2026-06-12-ecommerce-phase2-complete.md) | COMPLETE | `E:\Projects\e-commerse` |
| 2026-05-17 | [Kilo Workflow Setup](memory/tasks/2026-05-17-kilo-workflow-setup.md) | COMPLETE | — |

## Recent Activities

### Library CLI Final Report and Private Archive Refresh (2026-06-19)
- Final report committed locally as `a5f0472437b14e389eba795c09ddd5047f924ca7`; archive report committed through `afac34d`.
- Private tar.gz/ZIP archives regenerated and verified: final report present, `start.sh` mode preserved, stale/prohibited/generated entries absent, no remotes/no push.
- Lesson: archived reports should avoid exact archive byte sizes because report content becomes part of the archive and can cause size self-reference drift.

### Kilo Phase Accountability Workflow (2026-06-19)
- Added centralized `Documentation Accountability Contract` to `AGENTS.md`.
- Added phase accountability inserts to required agent files.
- Created `docs/2026_06_19_phase_accountability_workflow/` with all required phase artifacts.
- Lesson: verify `/output` carefully because a pre-existing directory may exist; confirm no task artifacts or session-modified files are under it.

### Task Architect Scale Category Enhancement (2026-06-21)
- Enhanced `agent/task-architect.md` so task-architect classifies work by scale category and designs Source → Spec → Impact research before implementation planning.
- Added scale-category matrix, research depth rules, structured template sections, and routing guidance for New Project, Enhancement, Refactor, Migration, Research, Debug, and Administration tasks.
- Lesson: scale category should drive research posture, specification rigor, agent mapping, and verification strategy rather than being treated as a passive label.

### Analyst Spec Artifact Assignment (2026-06-21)
- Updated task architecture and analyst planning rules so `data-analyst` creates the canonical `masterplan/01_specs.md` when assigned to the spec phase.
- Updated `AGENTS.md`, `agent/data-analyst.md`, `agent/pm-planner.md`, and `agent/task-architect.md` so the masterplan flow is: research/analysis → `masterplan/01_specs.md` → `masterplan/02_plan.md`.
- Lesson: `pm-planner` should consume the canonical spec artifact instead of planning implementation from analysis alone when formal specs are required.

### ARSENAL R5 System Integration Architecture (2026-07-17)
- **11-dimension architecture** for 22 IDS perimeter products on 337 hectares
- **CONDITIONAL GO** — 87/87 AC PASS, P22 SDPPI is deal-breaker
- **Key metrics:** 11,831W typ, 29,977m cable, 5,735 Mbps bandwidth, 86% rack utilization
- **Data sovereignty enforced:** LOCAL-FIRST 87%, 3 air-gapped segments, 5-level classification, 12 cloud controls
- **Maintainability enforced:** ONVIF/REST/SNMP abstraction, 24 swap procedures, 5-10yr lifecycle
- **Hidden costs revealed:** 61× FLIR encoder boards + 61× Axis DC PSU + 29,977m cable (187% over baseline)
- **Lesson:** Blueprint v2 insufficient — user demanded peta assignment delegasi (99-step table). Blueprint v3 with full delegation map = correct format for complex multi-dimension research.
- **Lesson:** Data sovereignty as mandatory constraint adds design depth but is essential for military IDS. Maintainability layer prevents vendor lock-in for 5-10 year lifecycle.

### E-commerce App Development (2026-06-12)
- **Phase 0 (Foundation):** Monorepo, NestJS backend skeleton, Next.js frontend, Prisma + SQLite, design system primitives, CI/CD — COMPLETE (`f2e17b9`)
- **Phase 1 (Auth & Users):** JWT RS256 auth, refresh rotation, argon2id, profile/addresses, frontend auth pages — COMPLETE (`6ee29fa`, `85b8364`)
- **Phase 2 (Catalog & Search):** Products/Categories/Brands CRUD, FTS5 search, Reviews module, Admin catalog management, frontend catalog pages/components — COMPLETE (`7c15c59`)
- **Phase 2 Code Review Fixes (ALL RESOLVED):**
  - Admin controllers refactored to service layer (AdminCategoriesService, AdminBrandsService)
  - Reviews cursor pagination refactored from offset-style to keyset (created cursor-pagination.util.ts)
  - parseJsonField extracted to common/utils/json.util.ts
  - FtsSyncService registered in CatalogModule, reindex endpoint added
  - Reviews moderation uses @Roles('ADMIN') decorator
  - Validation throws BadRequestException instead of plain objects
  - Schema reconciled via migration (added metaTitle, metaDescription, isFeatured, sessionId, isPrimary, isVerifiedPurchase, PROCESSING/CANCELLED PaymentStatus)
  - CategoryTreeEditor refactored (extracted CategoryFormModal, ReorderControls)
  - FTS error handling now logs warnings

### Previous Sessions...
    - Transformed AI Agent Preview backend into a reusable service for VPS/Kiloclaw.
    - Implemented Provider pattern for Runtime, Storage, and Auth.
    - Added Hybrid Auth (JWT + API Key) and Swagger documentation.
    - Established Docker/PM2 deployment and GitHub Actions CI/CD.
    - Verified end-to-end with automated tests.
- Completed UI/UX redesign for AI Agent Preview using Tailwind, jQuery, SweetAlert2.
  - Built design system (dark-mode-first RGB tokens), reusable components, refactored all pages.
  - Fixed hardcoded hex colors, PostCSS config, port conflicts (3101/3102 after restart).
  - Wrote Puppeteer UAT simulation → 5/5 steps pass.
  - All changes committed and apps running in background.
- **Previous session:** UI/UX redesign for Certification Marketplace using Tailwind CSS and React-native interactions; committed and pushed to GitHub (master branch).

### GSP Orchestration Project DOCX — Batch 5 Complete (2026-07-10)
- **Chapter 5 (Analisis Dua Jalur Orkestrasi)** appended to existing DOCX document
- 8 sections covering paid vs local path architecture, 8-dimension capability comparison (Tabel 5.1), 50-agent model mapping across 9 sub-tables (Tabel 5.2a-5.2i), fallback mechanism, architectural implications
- DOCX grew from 73KB → 87.7KB, 376 → 464 paragraphs, 9 → 19 tables
- Sources: `research/03_analysis.md`, `research/01_explore.md`, `masterplan/01_specs.md`
- Chapters 6-12 pending in sequential writing pipeline

## Key Lessons Learned
### AI Agent Preview (2026-05-18 to 2026-05-19)
1. **PostCSS config is required:** Tailwind 4 needs an explicit `postcss.config.js` (`plugins: { tailwindcss: {}, autoprefixer: {} }`). Zero-config builds can break silently.
2. **Verify ports before automation:** Use `Get-NetTCPConnection -State Listen` to confirm active ports before writing Puppeteer scripts that depend on them.
3. **jQuery in React/Vite:** Install via npm (`npm install jquery`), do NOT use CDN `<script>`. CDN + npm results in duplicate globals and erratic behavior.
4. **jsPDF in Vite:** Use `npm install jspdf`. CDN UMD version conflicts with ESM module resolution and fails silently during PDF generation.
5. **Puppeteer UAT reliability:** Always `await page.waitForSelector(selector)` before any `page.click()`; timeouts without explicit waits cause false-negative test results.
6. **Hex color elimination strategy:** Migrate hardcoded hex values component-by-component, then run a repo-wide grep (`rg '#[0-9a-fA-F]{6}'`) to catch any leftovers in a final sweep.
7. **Sequelize Class Fields Shadowing:** Declaring public class fields in TS models (e.g., `public id: number`) shadows Sequelize's internal getters/setters. Use the `declare` keyword to avoid `undefined` values on retrieved models.
8. **Provider Pattern for Reusability:** Abstracting infrastructure (Runtime, Storage, Auth) behind interfaces allows the service to remain agnostic of the specific environment and enables easy switching between providers (e.g., OpenClaw to KiloClaw).
9. **Hybrid Auth Flow**: Implementing a middleware that prioritizes API keys over JWTs allows seamless integration for both human users (web) and service-to-service calls (VPS/Kiloclaw).

### Certification Marketplace (Earlier session)
7. Semantic Tailwind colors (using `bg-color-foreground` / `text-color-muted`) ensure branding consistency across components.
8. LF vs CRLF line endings require Git config handling on Windows (`core.autocrlf`) to avoid spurious diffs.
9. React-native-style interactions (handler-driven) avoid DOM conflicts in Next.js / server-rendered projects.
10. Role‑aware navigation improves user experience by hiding/showing routes based on account type.
11. Global memory updates (MEMORY.md) help track progress and lessons across sessions and devices.

### Task Architect Scale Category Enhancement (2026-06-21)
1. Scale category should drive research posture, specification rigor, agent mapping, and verification strategy rather than being treated as a passive label.
2. Source → Spec → Impact research should be designed before implementation planning so evidence, acceptance criteria, and blast radius are explicit.

### Analyst Spec Artifact Assignment (2026-06-21)
1. `data-analyst` should create `masterplan/01_specs.md` when assigned to the spec phase.
2. `pm-planner` should consume `masterplan/01_specs.md` before creating `masterplan/02_plan.md`, rather than planning from analysis alone.

### ARSENAL Product Knowledge Base (2026-07-15)
- Completed comprehensive 22-product knowledge base with per-product 3-loop research architecture
- Key insight: **Per-product deep research loops prevent hallucination** — batching multiple products into single agent runs causes quality degradation
- 108 files produced across 7 phases (identification, research, masterplan, implementation, verification, report, decisions)
- Lesson: Always use specialist agents (data-collector, data-analyst, verifier) before falling back to general agents — specialist agents have stronger prompts and domain knowledge
- Lesson: OEM pattern in defense procurement: Chinese manufacturers (Uniview, Dahua) white-label through Singapore distributors (Heimdal Defence) to local integrators (GSP) — 3-57x markup common
- Lesson: TKDN compliance is critical for Indonesian government procurement — always check TKDN status early in vendor evaluation

### ARSENAL Product Alternative Research (2026-07-16)
- Completed second research phase: solve 15 problematic products + enrich 7 non-problematic products = 22/22
- **Potential savings: Rp 32.6 Miliar** via OEM Direct Procurement (5 products: P16 Rp 9.0B, P11 Rp 7-11B, P15 Rp 5.8B, P13 Rp 3.6B, P12 Rp 3.5B)
- **TKDN roadmap:** 22.7% (Y0) → 90.9% (Y4) via hybrid procurement + local assembly + manufacturer partnership
- **UU PDP compliance gaps** identified for 4 biometric products (P13/P15/P16/P18) — DPIA + DPO + consent mechanism needed
- **Key insight: Value justification > hard budget cap** — user prefers flexibility to justify feature value over rigid 15% cap
- **Key insight: Phase separation effective** — separating problematic from enrichment products yields more focused output
- **Key insight: Task-architect table format critical** — Step/Agent/DependsOn table format is far more executable than narrative format
- Lesson: Multi-pass research looping (no cap on passes) adds significant depth — 2-3 passes per product recommended
- Lesson: Documentation accountability (delegation_progress_report.md after each step) enables session resumability after interruption
- Lesson: Controller-friendly format matters — narrative blueprints are hard to execute; table-based blueprints with explicit Depends On chains are directly executable

### ARSENAL R3 — Component Decomposition (2026-07-16)
- 6D vendor scoring adds significant depth beyond base price — critical for defense procurement
- TKDN 3-track model (native + assembly + SDK) achieves 77.3% compliance from 22.7% baseline
- Component-level analysis reveals hidden costs: I/O boards sold separately (P20), HDD surge +46%
- Cross-product synthesis is where the real value is — standardization savings only visible at aggregate
- Per-product sequential loop confirmed effective across 3 research cycles (no hallucination)
- OEM identification enables direct procurement bypass (saves Rp 10-15B from 3-38x markup)
- Documentation accountability contract enables session resumability across complex multi-loop tasks

### Orchestration Issue Analysis (2026-07-16)
- Diagnosed 9 orchestration defects across 3 agents (RT, TA, MC) from GSP Arsenal R1-R3 runs
- **28 atomic fix contracts** in 2-wave implementation plan (Wave 0: 16 parallel, Wave 1: 12 sequential)
- **Wave 0 COMPLETE (2026-07-17):** TA (11 changes), RT (4 changes), AGENTS.md (1 change) — all verified PASS
- **Wave 1 COMPLETE (2026-07-17):** MC (12 changes to `master-controller.md`) — 12 fix contracts applied bottom-to-top: schema version check (MC-8C), enforcement checklist additions (MC-7C, MC-9D), two-phase documentation lifecycle (MC-9A), memory persistence in final report (MC-9B), controller-friendliness quality gate (MC-8B), PRE-HIL validation V1-V7 (MC-8A), BLUEPRINT_APPROVAL gate (MC-7A), blueprint sign-off classification (MC-7D), blueprint trigger phrases (MC-7B), Step 4 memory persistence (MC-9C), post-synthesis memory note (MC-9E)
- **Root cause #1: TA batching** — "3-7 subtasks" range permits multi-task batching, causing hallucination across all R1-R3 runs. Fix: replace with atomicity rule.
- **Root cause #2: TA narrative output** — template is 96.7% narrative; table format (proven critical in R2) is buried as subsection. Fix: enforce Step|Agent|DependsOn table-first format.
- **Root cause #3: MC Quality Gate fires too late** — validates 02_structured AFTER it's been used, not before HIL gate. Fix: add PRE-HIL VALIDATION step.
- **Root cause #4: MC zero memory persistence** — Documentation Lifecycle covers /docs only; knowledge lost after each session. Fix: add mandatory memory write at task completion.
- **Critical implementation order:** TA changes (Wave 0) must complete before MC changes (Wave 1) to avoid infinite re-delegation loops.

### Comprehensive Research Flow Enhancement (2026-07-09)
1. **task-architect is a design agent, NOT an execution agent.** The task-architect produces `identification/02_structured.md` (the delegation plan) but must NEVER modify application files, agent configs, or any file outside `/docs/`. File modifications are delegated by the master controller to `coder-execution` or appropriate executor agents.
2. **Post-research handoff flow:** task-architect refines structured task → master controller reads the plan → master controller delegates each implementation step to the executor agent specified in `Agent_to_Invoke` → master controller verifies delegation gate.
3. Added "Design vs Execution Boundary" section to `task-architect.md` with explicit MAY/MUST NOT rules.
4. Added "Post-Research Handoff Protocol" section to `master-controller.md` showing the delegation chain.
5. Added 7 canonical external research dimensions (Technology Trends, Technology Evaluation, Vendor Evaluation, Market Share, Regulatory, Competitive Landscape, Industry Trends) to 12 agent files.
