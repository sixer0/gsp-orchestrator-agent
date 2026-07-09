# GSP Orchestrator Agent

Multi-agent orchestration configuration repository for the Kilo runtime. Contains 51 agent definitions, 40+ specialized skill modules, 18 custom commands, and a complete phase-accountable workflow for automated software development, research, and documentation.

## Overview

This repository configures Kilo, an AI agent runtime, to operate as a structured multi-agent system. A master controller delegates work across a tiered team of specialized agents -- covering requirements analysis, task architecture, research, implementation, verification, security review, infrastructure operations, document processing, and image creation -- with outputs validated through a formal phase-gate process.

The system is designed for production-grade software engineering workflows where quality, traceability, and repeatability are required. Every task produces documented artifacts under a standardized `/docs` structure, ensuring full auditability of decisions, implementations, and verifications.

## Features

### Multi-Agent Orchestration

A master controller coordinates 51 specialized agents organized into 9 functional categories. Each agent has a defined accountability scope, a designated model (paid or local), and strict operational boundaries. The controller follows a tiered model: paid cloud models are preferred, with automatic fallback to local Ollama-provided variants when rate limits are hit.

### Phase Accountability Workflow

Every task passes through a structured 10-phase lifecycle: identification, research, masterplan, initialization, implementation, gateway check, test, verification, report, and decisions. Each phase requires specific artifacts under `/docs/[date]_[task]/[phase]/`. Phase gates enforce that required artifacts exist before the controller marks a phase complete.

### Seven External Research Dimensions

Agents that perform research (data-analyst, pm-analyst, data-collector, explore, task-architect) are trained on 7 canonical external research dimensions:

| Dimension | Focus |
|-----------|-------|
| 1. Technology Trends | Emerging technologies, language/ecosystem shifts, architectural patterns |
| 2. Technology Evaluation | Tool/library comparison, build-vs-buy, migration feasibility |
| 3. Vendor Evaluation | Vendor reputation, pricing, lock-in risk, support quality |
| 4. Market Share & Positioning | Adoption metrics, community size, market trajectory |
| 5. Regulatory & Compliance | Data sovereignty, licensing, export controls, accessibility |
| 6. Competitive Landscape | Competitor analysis, feature differentiation, moat assessment |
| 7. Industry Trends | Domain-specific patterns, business model shifts, best practices |

### Documentation Accountability Contract

Every agent delegation produces a `delegation_progress_report.md` in the task's `/docs` folder. Artifacts follow strict naming conventions (`snake_case`, zero-indexed numbering), are additive only, and are never written to `/output/`. The contract is enforced at the controller level before phase transitions.

### Free-Tier Fallback Architecture

Each paid cloud agent has a corresponding `*-local` variant configured to run on local Ollama models. The master controller attempts the paid agent first; if rate-limited or unavailable, it transparently falls back to the local variant. Local variants preserve the same workflow structure and accountability scope, with slightly condensed content to account for smaller context windows.

### Source-to-Spec-to-Impact Research

Before implementation begins, the system performs three layers of research design:

- **Source Research** (task-architect, explore, data-collector): Map the existing codebase, identify affected files, gather external references.
- **Specification** (data-analyst): Synthesize findings into formal specifications with acceptance criteria, boundary conditions, and edge-case analysis.
- **Impact Analysis** (pm-analyst, pm-planner): Assess blast radius, dependency chains, migration effort, and rollback strategy.

### Scale Category Classification

Every task is classified into one of 7 scale categories at the identification phase, which determines research depth, specification rigor, agent mapping, and verification posture:

| Category | Description | Research Depth |
|----------|-------------|----------------|
| New Project | Greenfield development | Maximum: full Source + Spec + Impact |
| Enhancement | Additive feature on existing code | Moderate: targeted source + spec |
| Refactor | Structural change, same behavior | Full: deep source + impact |
| Migration | Platform/language/dependency change | Full: all 7 external dimensions |
| Research | Feasibility, exploration, POC | Source + external research only |
| Debug | Bug reproduction and fix | Targeted: minimal source + spec |
| Administration | Config, docs, tooling | Minimal or none |

### Checkpoint Feedback Loops

Every verification step (code review, security review, cross-reference validation) has defined re-route paths. If a review finds issues, the system does not simply flag them -- it routes the task back to the appropriate agent with specific remediation instructions and re-verifies. The loop is bounded to 3 cycles before escalation.

### Professional Document Output

The document agent pipeline supports creation of professional `.docx` files with sequential chapter writing, table of contents generation, and templated report structures. The document-controller orchestrates reader, writer, converter, and reviewer agents for end-to-end document processing.

## Architecture

The following diagram shows the delegation flow for a typical task:

```
User Request
     |
     v
+------------------+
| Master Controller |  -- Gate keeper, phase enforcer, delegation dispatcher
+------------------+
     |
     v
+---------------------+
| Request Translator  |  -- Parse intent, build structured task description
+---------------------+
     |
     v
+------------------+
| Task Architect   |  -- Design blueprint: scale category, agent map, phases
+------------------+
     |
     +------------------------------------------+
     |                                          |
     v                                          v
+---------------+  +------------------+  +------------------+
| Explore       |  | Data Collector   |  | Data Analyst     |
| (map codebase)|  | (gather data)    |  | (synthesize)     |
+---------------+  +------------------+  +------------------+
     |                                          |
     +------------------------------------------+
     |
     v
+------------------+
| PM Analyst       |  -- Requirements, feasibility, risk
+------------------+
     |
     v
+------------------+
| PM Planner       |  -- Implementation plan with tracking
+------------------+
     |
     v
+------------------+
| Coder Execution  |  -- Implementation (may be multiple rounds)
+------------------+
     |
     +--------+--------+--------+
     |        |        |        |
     v        v        v        v
+--------+ +--------+ +--------+ +--------+
|Verifier| |Senior  | |Security| |Test    |
|        | |Reviewer| |Review  | |Expert  |
+--------+ +--------+ +--------+ +--------+
     |        |        |        |
     +--------+--------+--------+
     |
     v
+------------------+
| Master Controller|  -- Verify phase artifacts, close gates
+------------------+
     |
     v
+------------------+
| Report / Done    |
+------------------+
```

**Specialist agents** (git, docker, database, document, image) are invoked on demand by the controller or by executor agents during implementation and verification phases.

**PM Controller** and **Document Controller** are domain-specific orchestrators that handle PM/BA workflow and document lifecycle respectively, operating as sub-orchestrators under the master controller.

## Agent Catalog

### Orchestration Controllers

| Agent | Mode | Description |
|-------|------|-------------|
| `master-controller` | Primary | Orchestrates full development workflow; gate keeper, phase enforcer |
| `master-controller-local` | Primary | Fallback: local-tier master controller |
| `pm-controller` | Primary | PM/BA workflow orchestration |
| `pm-controller-local` | Primary | Fallback: local-tier PM/BA orchestrator |
| `document-controller` | Primary | Document lifecycle orchestration |
| `document-controller-local` | Primary | Fallback: local-tier document orchestrator |

### Translation & Architecture

| Agent | Mode | Description |
|-------|------|-------------|
| `request-translator` | Subagent | Parse user requests into structured tasks |
| `task-architect` | Subagent | Design structured task blueprint with agent mapping |

### Research & Analysis

| Agent | Mode | Model | Description |
|-------|------|-------|-------------|
| `explore` | Subagent | Ollama GSP General | Map codebase structure and report |
| `data-collector` | Subagent | Ollama GSP General | Systematic data gathering |
| `data-analyst` | Subagent | DeepSeek V4 Pro | Synthesize analysis and specifications |
| `data-analyst-local` | Subagent | Ollama GSP Senior Analyst | Local fallback for analysis |

### PM / Business Analysis

| Agent | Mode | Description |
|-------|------|-------------|
| `pm-analyst` | Subagent | Requirements, feasibility, risk analysis |
| `pm-analyst-local` | Subagent | Local fallback for PM analysis |
| `pm-planner` | Subagent | Implementation plan creation |
| `pm-planner-local` | Subagent | Local fallback for planning |
| `pm-verifier` | Subagent | Document completeness and quality verification |
| `pm-verifier-local` | Subagent | Local fallback for verification |
| `pm-writer` | Subagent | Report and document creation |
| `pm-writer-local` | Subagent | Local fallback for document writing |

### Code Implementation & Verification

| Agent | Mode | Model | Description |
|-------|------|-------|-------------|
| `coder-execution` | Subagent | DeepSeek V4 Flash | Code implementation |
| `coder-execution-local` | Subagent | Ollama GSP Executor | Local fallback for implementation |
| `senior-code-reviewer` | Subagent | DeepSeek V4 Flash | Code review: duplication, maintainability, dependencies |
| `senior-code-reviewer-local` | Subagent | Ollama GSP Senior Analyst | Local fallback for code review |
| `verifier` | Subagent | Stepfun Step 3.7 Flash | Verification and testing |
| `verifier-local` | Subagent | Ollama GSP General | Local fallback for verification |
| `security-review` | Subagent | Stepfun Step 3.7 Flash | Security vulnerability scanning |
| `security-review-local` | Subagent | Ollama GSP Senior Analyst | Local fallback for security review |
| `test-expert` | Subagent | Xiaomi Mimo V2.5 Pro | Test generation and strategy |
| `test-expert-local` | Subagent | Ollama GSP General | Local fallback for test generation |

### Infrastructure Specialists

| Agent | Mode | Description |
|-------|------|-------------|
| `git-specialist` | Subagent | Git operations (status, diff, branch, merge) |
| `git-specialist-local` | Subagent | Local fallback for git operations |
| `docker-specialist` | Subagent | Container and Docker Compose operations |
| `docker-specialist-local` | Subagent | Local fallback for Docker operations |
| `database-specialist` | Subagent | Schema, migration, query, seed operations |
| `database-specialist-local` | Subagent | Local fallback for database operations |

### Document Processing

| Agent | Mode | Description |
|-------|------|-------------|
| `document-reader` | Subagent | Parse PDF, DOCX, XLSX, PPTX documents |
| `document-reader-local` | Subagent | Local fallback for document reading |
| `document-writer` | Subagent | Create and edit office documents |
| `document-writer-local` | Subagent | Local fallback for document writing |
| `document-converter` | Subagent | Convert between document formats |
| `document-converter-local` | Subagent | Local fallback for document conversion |
| `document-reviewer` | Subagent | Review and revise documents |
| `document-reviewer-local` | Subagent | Local fallback for document review |
| `document-translator` | Subagent | Parse and structure document requests |
| `document-analyst` | Subagent | Assess document quality and relevance |
| `document-analyst-local` | Subagent | Local fallback for document analysis |

### Image Processing

| Agent | Mode | Description |
|-------|------|-------------|
| `image-specialist` | Subagent | Image creation, editing, manipulation |
| `image-specialist-local` | Subagent | Local fallback for image operations |
| `image-analyst` | Subagent | Image analysis and extraction |
| `image-analyst-local` | Subagent | Local fallback for image analysis |

### Default Agents (Built-in)

| Agent | Model | Description |
|-------|-------|-------------|
| `ask` | Kilo auto (free) | General Q&A |
| `plan` | Ollama GSP Senior Analyst | Planning agent |
| `debug` | Stepfun Step 3.7 Flash | Debugging agent |
| `orchestrator` | DeepSeek V4 Pro | General orchestrator |
| `code` | Ollama GSP Executor | Code agent |

### Agent Configuration Summary

| Property | Value |
|----------|-------|
| Total agent files | 51 |
| Primary agents | 5 (master, pm-controller, pm-controller-local, document-controller, document-controller-local) |
| Subagent pairs (primary + local) | 17 pairs (34 files) |
| Standalone subagents | 5 (request-translator, task-architect, explore, data-collector, image-analyst, image-analyst-local, document-translator) |
| Default built-in agents | 5 (ask, plan, debug, orchestrator, code) |

## Skills

Skills extend agent capabilities without repeating workflow logic in prompts. The repository registers 40+ skill modules in `kilo.json`.

### Orchestration & Workflow

| Skill | Purpose |
|-------|---------|
| `orchestrator-worker` | Delegate complex tasks to specialist sub-agents |
| `plan-and-execute` | Decompose tasks into staged, dependency-aware execution plans |
| `checkpoint-resume` | Persist workflow state at checkpoints for interrupt/resume |
| `self-healing-loop` | Classify and recover from execution failures |
| `context-engineering` | Manage long-running agent context to prevent token overflow |
| `reflection-loop` | Self-critique with evidence-based revision |
| `brainstorming` | Explore user intent, requirements, and design before creative work |
| `writing-plans` | Create multi-step execution plans from specs |

### Development & Quality

| Skill | Purpose |
|-------|---------|
| `backend-execution` | Production-grade backend API implementation (Node/TS) |
| `tdd` | Test-driven development (red-green-refactor) |
| `dry-run-verify-fix` | Validate changes with simulated execution before delivery |
| `eval-driven-improver` | Benchmark and iteratively improve skill quality |
| `skill-creator-kilo` | Create and improve Kilo SKILL.md files |
| `tool-design-optimizer` | Refine tool names, schemas, and descriptions |
| `agent-md-refactor` | Refactor bloated agent instruction files |
| `code-review-senior` | Senior code review with dependency impact analysis |
| `receiving-code-review` | Process incoming code review feedback |
| `requesting-code-review` | Request code review before merging |

### Frontend & Design

| Skill | Purpose |
|-------|---------|
| `frontend-design` | High-level visual design principles and direction |
| `design-taste-frontend` | Anti-slop frontend rules for landing pages and portfolios |
| `frontend-integration` | Connect UI components to backend API endpoints |
| `webapp-testing` | Playwright-based local web app testing |

### Safety & Security

| Skill | Purpose |
|-------|---------|
| `human-in-loop-gate` | Pause and request user input for critical decisions |
| `security-review-gate` | Pre-flight security review for destructive or external actions |

### Document & Content

| Skill | Purpose |
|-------|---------|
| `docx` | Professional DOCX generation with sequential chapter writing |
| `pdf` | PDF reading and manipulation |
| `pptx` | PowerPoint presentation generation |
| `xlsx` | Excel spreadsheet reading and manipulation |
| `content-research-writer` | Research-backed content writing with citations |
| `canvas-design` | Visual art creation in PNG and PDF |
| `image-enhancer` | Image resolution, sharpness, and clarity enhancement |

### Browser & Automation

| Skill | Purpose |
|-------|---------|
| `agent-browser` | Headless browser automation for web interaction |
| `mcp-integration` | Configure and manage MCP server connections |

### Deployment & Operations

| Skill | Purpose |
|-------|---------|
| `deploy-to-vercel` | Deploy applications and websites to Vercel |
| `setup-pre-commit` | Configure Husky pre-commit hooks with lint-staged |
| `using-git-worktrees` | Create isolated workspaces via git worktree |
| `finishing-a-development-branch` | Decide merge/PR/cleanup strategy |
| `observability-tracer` | Record tool calls and state transitions for debugging |

### Verification

| Skill | Purpose |
|-------|---------|
| `verification-before-completion` | Run verification commands before claiming work complete |
| `diagnosing-bugs` | Systematic diagnosis for bugs and regressions |

### Domain-Specific

| Skill | Purpose |
|-------|---------|
| `to-prd` | Convert conversation into a published PRD |
| `to-issues` | Break plans into independently-grabbable issues |

## Commands

Custom commands provide quick access to common workflows:

| Command | Description |
|---------|-------------|
| `plan` | Create implementation plans |
| `explore` | Explore codebase structure |
| `search-code` | Search code with patterns |
| `explain` | Explain code in detail |
| `refactor` | Execute refactoring |
| `security` | Run security review |
| `test-gen` | Generate test files |
| `debug` | Debug issues |
| `git-status` | Show git working tree status |
| `git-log` | Display git log |
| `deps` | Analyze dependencies |
| `perf` | Performance analysis |
| `rollback` | Rollback changes |
| `doc` | Documentation operations |
| `quick-review` | Quick code review |
| `commit` | Commit with conventions |
| `delegate` | Delegate to sub-agents |
| `trading` | Trading operations |

## Configuration

### Model Tiering

The system uses a tiered model strategy:

- **Paid cloud models**: DeepSeek V4 Pro/Flash, Stepfun Step 3.7 Flash, Xiaomi Mimo V2.5 Pro, Nemotron 3 Super 120B
- **Free cloud models**: Kilo auto free tier
- **Local Ollama models**: GSP General, GSP Executor, GSP Senior Analyst, Qwen 3.6, DeepSeek R1 70B

The master controller (`kilo.json`) selects the paid model first. If rate-limited, it falls back to the `*-local` variant using Ollama-provided models.

### Permissions

| Permission | Scope |
|------------|-------|
| Read/Glob/Grep/List | Full workspace |
| Edit/Write | Full workspace |
| Bash | Full workspace |
| Web search/fetch | Allowed |
| Puppeteer | Navigation, screenshots, clicks, fills |
| Skill/Task | Registered skills and sub-agents |

### Memory System

```
MEMORY.md              # Master index: table of contents, summaries
memory/
  YYYY-MM-DD.md        # Daily log: proactive reminders
  refs/                # Library: technical deep-dives
  tasks/               # Archive: task reports and compaction snapshots
```

## Getting Started

### Prerequisites

- [Kilo runtime](https://kilo.ai) for full orchestration
- [Ollama](https://ollama.ai) (optional, for local fallback agents)

### Local Setup

1. Clone the repository:
   ```
   git clone https://github.com/sixer0/gsp-orchestrator-agent.git
   ```

2. (Optional) Pull local Ollama models for fallback agents:
   ```
   ollama pull gsp-general:latest
   ollama pull gsp-executor:latest
   ollama pull gsp-senior-analyst:latest
   ```

3. Configure `kilo.json` to point to your Ollama instance if using local models:
   ```json
   {
     "provider": {
       "ollama": {
         "options": {
           "baseURL": "http://localhost:11434/v1"
         }
       }
     }
   }
   ```

### Usage

To start a task through the orchestration pipeline, invoke the master controller:

```
kilo "Implement feature X" --agent master-controller
```

The controller will automatically:
1. Delegate to `request-translator` for intent parsing
2. Pass to `task-architect` for blueprint design
3. Route through research, planning, execution, and verification phases
4. Produce artifacts under `docs/[date]_[task]/`

Alternatively, use a domain-specific controller:

```
kilo "Write a project proposal" --agent pm-controller
kilo "Convert DOCX to PDF" --agent document-controller
```

### Customizing Agents

Agent definitions live in `agent/` as Markdown files with YAML frontmatter. Each file specifies:

```yaml
---
name: agent-name
description: Purpose description
mode: primary | subagent
steps: <max-step-count>
color: "#HEXCOLOR"
model: provider/model:variant
---
```

To add a new agent, create a file in `agent/` and register it in `kilo.json` under the `"agent"` key.

## Repository Structure

```
.
+-- AGENTS.md              Global rules, memory management, documentation contract
+-- SOUL.md                Agent personality and boundaries
+-- MEMORY.md              Knowledge index
+-- kilo.json              Kilo runtime configuration
+-- kilo.jsonc             JSONC config (not committed)
+-- provider-config.yaml   Provider configuration
+-- README.md              This file
+-- CHANGELOG.md           Release history
+-- IDENTITY.md            Agent identity definition
+-- HEARTBEAT.md           Heartbeat tracking
+-- EXAMPLES_GALLERY.md    Example outputs
+-- package.json           npm dependencies
+-- agent/                 51 agent definition files
+-- skills/                40+ skill modules
+-- command/               18 command definitions
+-- docs/                  Task documentation artifacts
+-- memory/                Daily logs, references, task archives
+-- masterplan/            Implementation plan artifacts
+-- verification/          Verification artifacts
+-- output/                Runtime output (gitignored)
+-- memory/                Daily logs, refs, tasks
```

## License

This is a private configuration repository. Agent definitions, skill modules, and orchestration workflows are proprietary. Refer to individual agent files for reuse terms where applicable.

---

*For questions, issues, or contributions, open an issue on the repository or contact the repository maintainer.*
