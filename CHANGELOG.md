# Changelog

Semua perubahan penting pada repository ini akan didokumentasikan di file ini.

Format: [Keep a Changelog](https://keepachangelog.com/id-ID/)

## [2026-07-20]

### Ditambahkan
- **Document Quality Standards Skill** (`skills/document-quality-standards/SKILL.md`) — 1419 lines, 10 modules
  - Module A: Document type classification (8 types: research, proposal, report, technical, etc.)
  - Module B: Independence tiers (6 levels: self-contained to fully-dependent)
  - Module C: Information processing (evidence handling, source confidence levels)
  - Module D: Writing principles (structure, clarity, anti-AI patterns)
  - Module E: Depth control (audience-adaptive: executive, technical, end-user)
  - Module F: Quality validation checklists (10-point internal + 6-point external)
  - Module G: Reference handling (citation format, cross-references)
  - Module H: Anti-AI writing standards (GSP company style: long sentences, "Kami" voice, confidence labels)
  - Module I: Document formatting & styling (Indonesian professional docs, cover page, formal letter)
  - Module J: Markdown & DOCX output standards
- **Document Translator Local Agent** (`agent/document-translator-local.md`) — Local fallback for document translation
- **Parallel Delegation Race Condition Fixes** — 8 vectors identified and fixed
  - Per-agent output partitioning (`delegation_progress/<agent>.md`)
  - Controller-mediated writes for shared files
  - Immutable snapshots during artifact refinement
  - Phase 0d: Parallel Output Isolation in orchestrator-worker skill
  - Phase 0d.1: Concurrency Enforcement with hard limits
- **Concurrency Limits** — Server capacity protection
  - Max 2 parallel tasks per same agent type
  - Max 4 parallel tasks total across different agent types
  - Wave-based batching strategy for overflow

### Diubah
- **Orchestrator Worker Skill** (`skills/orchestrator-worker/SKILL.md`)
  - Added Phase 0d: Parallel Output Isolation (5 isolation rules)
  - Added Phase 0d.1: Concurrency Enforcement (hard limits, batching strategy)
  - Added pre-parallel checklist and post-parallel synthesis checklist
  - Added 4 anti-pattern rows for race conditions
- **Master Controller** (`agent/master-controller.md`)
  - Added Section 3: Parallel Delegation Output Isolation
  - Updated Documentation Contract with parallel delegation rules
  - Updated Sub-Agent Completion Gate with parallel gate criteria (items 6-8)
  - Added shared file ownership table and concurrency limits
- **Master Controller Local** (`agent/master-controller-local.md`)
  - Mirrored all master-controller.md changes
- **12 Document Agent Files** — Added Skill Awareness sections referencing document-quality-standards
  - document-analyst.md, document-analyst-local.md
  - document-controller.md, document-controller-local.md
  - document-reader.md
  - document-reviewer.md, document-reviewer-local.md
  - document-translator.md
  - document-writer.md, document-writer-local.md
  - document-analyst.md, document-analyst-local.md
  - pm-writer.md
- **Content Research Writer Skill** (`skills/content-research-writer/SKILL.md`)
  - Added quality standards integration reference
  - Added evidence-based writing rules (facts vs assumptions, source confidence)
  - Fixed pre-publish checklist indentation
- **MEMORY.md** — Added task reports for document quality standards and parallel delegation fixes

## [2026-05-15]

### Ditambahkan
- **Agent Nailla CS** (`agents/nailla-cs.yaml`) - Agent customer service untuk portfolio Sixer0
  - Personality: Perempuan, usia 23 tahun, ramah dan professional
  - Aturan: No pricing, no detailed tech tutorials, escalation untuk hiring interest
- **Agent SixerBot CS** (`agents/sixerbot-cs.yaml`) - Agent customer service alternatif
- **Memory System** (`memory/refs/`, `memory/tasks/`) - Sistem dokumentasi terstruktur
  - `nailla-agent-setup.md` - Panduan setup agent Nailla
  - `office-utils.md` - Dokumentasi office utilities
  - `onedrive-excel-workflow.md` - Workflow Excel dengan OneDrive
- **Scripts**
  - `office_utils.py` - Manipulasi file xlsx/docx/pptx/pdf + chart generation
  - `chat-widget.js` - Frontend chat widget untuk website
  - `nailla-api.php` - Backend API untuk routing pesan
  - `setup-nailla-agent.js` - Script setup agent
- **Skills**
  - `skills/ms365/` - Microsoft 365 integration skill (updated)
- **Documentation**
  - `AGENTS.md` - Panduan workspace
  - `SOUL.md` - Identitas agent
  - `USER.md` - Informasi pengguna
  - `IDENTITY.md` - Konfigurasi identitas
  - `TOOLS.md` - Environment dan tools
  - `MEMORY.md` - Memori jangka panjang
  - `HEARTBEAT.md` - Checklist heartbeat

### Diubah
- Struktur repository diorganisir lebih terstruktur
- `.gitignore` diperbarui untuk mengecualikan:
  - `openclaw-config/` (repo terpisah untuk config rahasia)
  - `__pycache__/`, `*.pyc` (Python cache)

### Dihapus
- Struktur lama `workspace-backup/` digantikan dengan struktur langsung di root

## Repository Info

- **Nama**: myagent-config
- **Pemilik**: sixer0
- **Tujuan**: Menyimpan konfigurasi OpenClaw yang dikustomisasi