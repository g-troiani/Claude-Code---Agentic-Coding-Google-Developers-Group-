# [Project Name] - Implementation Plan

This ExecPlan is a living document maintained in accordance with PLANS.md. The sections Progress, Surprises and Discoveries, Decision Log, and Outcomes and Retrospective must be kept up to date as work proceeds. All content required to implement this system is contained within this document; no external references are needed.

**SECURITY WARNING:** NEVER put API keys, secrets, URLs with credentials, or any sensitive values in this file or any file that will be committed to git. All credentials belong ONLY in .env files which are gitignored. Use placeholders like `$YOUR_KEY` or `<your-api-key>` when documenting commands that require credentials.


## IMPORTANT: Before Starting Any Work

**You MUST read the external memory before implementing any milestone or making changes.**

1. **Always read first:**
   - `.claude/memory/INDEX.md` — Overview of all archived content
   - `.claude/memory/decisions/architecture.md` — Architectural constraints
   - `.claude/memory/decisions/technology.md` — Stack choices and rationale

2. **Then read based on your task:**
   <!-- CUSTOMIZE: Map your feature areas to memory files -->
   - [Feature Area 1] work → `.claude/memory/milestones/[feature-area-1].md`
   - [Feature Area 2] work → `.claude/memory/milestones/[feature-area-2].md`
   - Database changes → `.claude/memory/schemas/database.md`
   - API changes → `.claude/memory/schemas/api.md`
   - Testing work → `.claude/memory/quality/testing.md`

3. **Why this matters:** This EXECPLAN is intentionally slim (~500 lines). Full implementation details, decisions, and patterns are archived in `.claude/memory/`. Reading the archives prevents repeating mistakes and ensures consistency with past decisions.

4. **ALWAYS spawn 3 scout subagents before implementing ANY milestone:**

   | Agent | Focus | Searches |
   |-------|-------|----------|
   | **Decisions Scout** | Constraints & trade-offs | `decisions/*.md` |
   | **Patterns Scout** | Implementation precedents | `milestones/*.md` |
   | **Schema Scout** | Data structures & APIs | `schemas/*.md`, `reference/*.md` |

   **This is mandatory. Do NOT skip.** Failing to understand the memory will break the repo.

See CLAUDE.md "Memory System" section for complete protocol.


## Purpose and Big Picture

<!-- CUSTOMIZE: Replace with your project description -->
[Brief description of what users do with your system and what value it provides.]

**Core workflow:** [Step 1] → [Step 2] → [Step 3] → [Outcome]

**Problems solved:**
1. [Problem 1]
2. [Problem 2]
3. [Problem 3]

**Key features:**
<!-- CUSTOMIZE: List your main features, mark which are implemented -->
- [ ] [Feature 1]
- [ ] [Feature 2]
- [ ] [Feature 3]


## Progress

<!-- CUSTOMIZE: Track your milestone completion here -->
**[Number] milestones complete.** For detailed notes, see `.claude/memory/milestones/` and `.claude/memory/quality/`.

| Phase | Milestones | Date | Archive |
|-------|------------|------|---------|
| [Phase 1 Name] | M1-M[X] | [Date] | `[archive-file].md` |
| [Phase 2 Name] | M[X+1]-M[Y] | [Date] | `[archive-file].md` |

### [Current/Recent Milestone Group]: [Name] (Status)

<!-- CUSTOMIZE: Document your current work here -->
[Brief description of what this milestone group accomplishes.]

**Results:** [Summary of what was achieved]

**Full archive:** `.claude/memory/milestones/[relevant-file].md`


## Surprises and Discoveries

Key lessons learned during implementation:

<!-- CUSTOMIZE: Document your lessons learned here. Categories are suggestions. -->

**Environment & Configuration:**
- [Lesson about env setup]
- [Lesson about configuration]

**[Your Database/Backend Service]:**
- [Lesson learned]
- [Gotcha to watch for]

**[Your Frontend Framework]:**
- [Lesson learned]
- [Compatibility note]

**[Your External APIs/Services]:**
- [Rate limit lesson]
- [API behavior lesson]

**[Authentication/Security]:**
- [Security lesson]
- [Auth gotcha]

**[Infrastructure/Deployment]:**
- [Deployment lesson]
- [Infrastructure gotcha]


## Known Issues and Future Improvements

<!-- CUSTOMIZE: Document active issues and planned improvements -->

**CRITICAL: [Issue Name]**
- **Issue:** [Description of the problem]
- **Risk:** [What could go wrong]
- **Current mitigations:**
  - [Mitigation 1]
  - [Mitigation 2]
- **Recommended improvements:**
  1. [Improvement 1]
  2. [Improvement 2]

**[Category] Requirements:**
- **Target:** [Your target metric]
- [Notes about current state and needed improvements]


## Decision Log

**Full archive:** `.claude/memory/decisions/`

<!-- CUSTOMIZE: Log your key decisions here -->
| Decision | Rationale | Archive |
|----------|-----------|---------|
| [Decision 1] | [Why you made this choice] | `[file].md` |
| [Decision 2] | [Why you made this choice] | `[file].md` |
| [Decision 3] | [Why you made this choice] | `[file].md` |


## Outcomes and Retrospective

**Full archive:** `.claude/memory/reference/retrospective.md`

<!-- CUSTOMIZE: Summarize retrospectives here -->
[Summary of what worked, what didn't, and key lessons from completed phases.]


## Context and Orientation

**Full archive:** `.claude/memory/reference/context.md`

<!-- CUSTOMIZE: Brief system description for onboarding -->
[Brief description of your system: tech stack, key concepts/glossary, project structure.]


## Milestone Quick Reference

<!-- CUSTOMIZE: Summary table of all milestones -->
**[X] milestones complete.** Production: [your-production-url]

| Range | Feature | Key Components |
|-------|---------|----------------|
| M1-M[X] | [Phase 1 Name] | [Key components built] |
| M[X+1]-M[Y] | [Phase 2 Name] | [Key components built] |


## Development Commands Reference

<!-- CUSTOMIZE: Your CLI/development commands -->

**CLI commands (if applicable):**

```
[command 1]     # Description
[command 2]     # Description
[command 3]     # Description
```

**How to run development server:**

```bash
cd [directory]/

# Option 1: With explicit environment variables
[ENV_VAR]="$YOUR_VALUE" \
[ENV_VAR_2]="$YOUR_VALUE_2" \
[start command]

# Option 2: Unset stale variables first
unset [ENV_VAR] [ENV_VAR_2]
[start command]

# Option 3: Just run (if no conflicting shell variables)
[start command]
```

The app runs at [local-url]

**Important:** [Any important notes about development setup]


## Recovery Notes

<!-- CUSTOMIZE: Document recovery procedures -->
- [Recovery procedure 1]
- [Recovery procedure 2]
- [What happens on failure scenario 1]
- [What happens on failure scenario 2]
- [Backup procedures]


## Memory Index

External memory in `.claude/memory/` ([X]+ files):

<!-- CUSTOMIZE: List your memory files -->
| Category | Files |
|----------|-------|
| `milestones/` | [list your milestone files] |
| `decisions/` | architecture.md, technology.md, patterns.md |
| `schemas/` | database.md, api.md, components.md |
| `reference/` | context.md, retrospective.md |
| `quality/` | testing.md |

See `.claude/memory/INDEX.md` for full summaries and cross-references.


## Infrastructure Reference

**Full specs:** See Infrastructure Milestones section below.

<!-- CUSTOMIZE: Your deployment summary -->
Deploy to production: [Frontend host] + [Backend host] + [Database host]. Cost: [estimate].

### Infrastructure Milestones

<!-- CUSTOMIZE: Your infrastructure milestones -->
| ID | Description | Status |
|----|-------------|--------|
| I1 | [Infrastructure task 1] | [ ] Pending |
| I2 | [Infrastructure task 2] | [ ] Pending |
| I3 | [Infrastructure task 3] | [ ] Pending |
| I4 | [Infrastructure task 4] | [ ] Pending |

**Production URLs:**
- Frontend: [your-frontend-url]
- Backend: [your-backend-url]

### Deployment Prerequisites

<!-- CUSTOMIZE: Your deployment checklist -->
- [ ] [Prerequisite 1]
- [ ] [Prerequisite 2]
- [ ] [Prerequisite 3]


## Artifacts and Notes

**Full schema archive:** `.claude/memory/schemas/`
- `database.md` - [Your database schema description]
- `api.md` - [Your API description]
- `components.md` - [Your component hierarchy description]

<!-- CUSTOMIZE: Quick reference for key algorithms/patterns -->
**[Algorithm/Pattern] Quick Reference:**
- [Key point 1]
- [Key point 2]

**[Status/State] Values:**
- [state 1] → [state 2] → [state 3] → [final state] (or error)


## Operational Policies (DO NOT DELETE)

These policies are ACTIVE and must be followed by every session. They are not milestones—they define ongoing operational behavior.


### Memory System Architecture

These milestones implement a tiered memory system to manage EXECPLAN complexity. The pattern adapts MemGPT's "LLM as Operating System" architecture for file-based Claude Code: core memory (always loaded) plus external memory (retrieved on demand). After completion, EXECPLAN.md shrinks from ~1500 lines to ~400 lines of active content while preserving full historical access.

**Architecture:**

    ┌─────────────────────────────────────────────────────────┐
    │                    CORE MEMORY                          │
    │              (Always in context)                        │
    ├─────────────────────────────────────────────────────────┤
    │  CLAUDE.md          │  EXECPLAN.md (slim)               │
    │  - Instructions     │  - Active state                   │
    │  - Memory access    │  - Current milestones             │
    │  - Conventions      │  - Known issues                   │
    └─────────────────────────────────────────────────────────┘
                              │
                              │ Read on demand
                              ▼
    ┌─────────────────────────────────────────────────────────┐
    │                  EXTERNAL MEMORY                        │
    │              (.claude/memory/)                          │
    ├─────────────────────────────────────────────────────────┤
    │  milestones/          │  decisions/                     │
    │  schemas/             │  reference/                     │
    └─────────────────────────────────────────────────────────┘


### Cleanup Loop (repeat after each milestone)

    Work → Archive → Slim → Repeat

After completing ANY milestone:
1. Archive detailed implementation notes to `.claude/memory/milestones/`
2. Extract new decisions to `decisions/*.md`
3. Update schemas if structure changed
4. Slim EXECPLAN.md - replace archived content with one-liner + link
5. Update INDEX.md if new files created

Target: Keep EXECPLAN.md under ~650 lines. If it grows larger, archive completed work immediately.


### Slim EXECPLAN to Active Content Only (OPERATIONAL POLICY - DO NOT DELETE)

EXECPLAN.md should contain only active work content. Target: ~500-650 lines.

**Sections to keep:**
- Purpose and Big Picture (concise system description)
- Progress (summary table with links to memory)
- Known Issues and Future Improvements (active guidance)
- Surprises and Discoveries (operational knowledge)
- Memory Index (links to all `.claude/memory/` files)
- Development Commands Reference (operational docs)
- Recovery Notes (operational docs)
- Operational Policies (this section and Memory Access Protocols)
- Infrastructure Reference (deployment procedures)

**Sections to archive:**
- Detailed milestone phase-by-phase notes → `milestones/*.md`
- Full Decision Log → `decisions/*.md`
- Detailed Outcomes and Retrospective → `reference/retrospective.md`
- Full Context and Orientation → `reference/context.md`
- Full schema details → `schemas/*.md`

**When adding new milestones:**
1. Add full detail during active development
2. After completion, archive to appropriate memory file
3. Replace with one-line summary + link to archive
4. Update Memory Index if new files created

**Verification:** Keep EXECPLAN.md under 650 lines. Run `wc -l EXECPLAN.md` to check.


### Memory Access Protocols (OPERATIONAL POLICY - DO NOT DELETE)

This section defines how to use the memory system. These protocols are ACTIVE and must be followed by every session.

**Starting New Work Protocol (IMPORTANT):**

Before implementing a new milestone, PROACTIVELY read relevant memory:

1. **Always read first:**
   - `.claude/memory/INDEX.md` - orient to available memory
   - `decisions/architecture.md` - check architectural constraints
   - `decisions/technology.md` - verify stack choices still apply

2. **Read based on work type:**
   <!-- CUSTOMIZE: Map your feature areas -->
   - [Area 1] work → `milestones/[area-1].md`
   - [Area 2] work → `milestones/[area-2].md`
   - Database changes → `schemas/database.md`
   - API changes → `schemas/api.md`
   - New features → `reference/research.md`

3. **Check for patterns:**
   - Similar past milestones for implementation patterns
   - Related decisions for constraints and trade-offs
   - Known issues that may affect new work

4. **Spawn scout subagents (for complex milestones):**

   For milestones with 3+ work items or cross-cutting concerns, spawn 3 parallel subagents to search archived memory. Each agent receives the milestone goal and work items.

   | Agent | Focus | Searches | Returns |
   |-------|-------|----------|---------|
   | **Decisions Scout** | Constraints & trade-offs | `decisions/*.md` | Relevant constraints, past rationale |
   | **Patterns Scout** | Implementation precedents | `milestones/*.md` | Similar past work, reusable patterns, gotchas |
   | **Schema Scout** | Data structures & APIs | `schemas/*.md`, `reference/*.md` | Affected tables, endpoints, type definitions |

   **Subagent prompt template:**
   ```
   MILESTONE: [ID and title]
   GOAL: [the "At the end of this milestone..." statement]
   WORK ITEMS: [list of tasks]

   Search .claude/memory/[your-area]/ and return:
   1. RELEVANT: Items that directly affect this milestone
   2. CONSTRAINTS: Rules/decisions we must follow
   3. PATTERNS: Similar past implementations to reference
   4. RISKS: Potential conflicts or issues to watch for

   Be specific. Quote file paths and line references.
   ```

   **Workflow:**
   1. Read EXECPLAN.md milestone description
   2. Spawn 3 scouts in parallel (single message, multiple Task calls)
   3. Wait for all results
   4. Synthesize: conflicts? missing info? clear to proceed?
   5. If clear → implement with focused context
   6. If conflicts → resolve before coding

### Reactive Retrieval Triggers

Also read external memory when:
1. User asks about completed features
2. You encounter unexpected behavior
3. You're unsure about prior decisions
4. Debugging requires implementation context

### Memory Update Protocol

After completing work:
1. Archive detailed notes to appropriate memory file
2. Update EXECPLAN.md Progress (keep concise - link to archive)
3. Update INDEX.md if new file created
4. Add new decisions to decisions/*.md with rationale

**Writing style for memory:** Be concise. Sacrifice grammar for brevity but explain the system thoroughly and preserve full meaning. Use tables, bullet points, code snippets over prose. Link to source files with line numbers. Future sessions need context, not narrative.


### Test-Driven Development (OPERATIONAL POLICY - DO NOT DELETE)

**TDD is mandatory for EVERY milestone.** No milestone is complete without passing tests. Write tests BEFORE implementing features. Use two test types: **Logic Tests** (automated) and **UI Tests** (browser automation).

**Agent Separation Policy (MANDATORY):**
The agent that writes tests MUST be different from the agent that implements the solution. This prevents bias. For every milestone:
1. Spawn **Test Agent** first to write failing tests based on requirements
2. Spawn **Implementation Agent** to write code that passes the tests
3. Test Agent reviews coverage and adds edge cases

**Real Data Policy (MANDATORY):**
NEVER use mock data when real services are available. This applies to EVERYTHING - databases, APIs, storage, auth, any service. If a real endpoint/service exists, use it.

**Only mock when absolutely necessary:**
- External paid APIs to avoid CI costs
- Time-sensitive operations (use fixed timestamps)
- Network failure scenarios (error handling tests)
- Third-party services with no test environment

**Two Test Types:**

| Type | Tool | Purpose | When Required |
|------|------|---------|---------------|
| **Logic Tests** | [your test tools] | Verify business logic, APIs, hooks, data transformations | Every code change |
| **UI Tests** | Chrome extension, Playwright | Verify visual rendering, user flows, interactions | Every UI change |

**Alternative: MCP Tools for Testing**
The system has access to MCP browser automation tools (Chrome extension). If these are faster or more advantageous for a specific test scenario, use them instead of or alongside traditional test frameworks.

**UI Testing Permission:** The system has standing permission to use Chrome browser automation for UI testing without additional approval.

**Modified Cleanup Loop:**

    Work → Logic Test → UI Test → Archive → Slim → Repeat
                 ↑           ↑
                 └───────────┴─ Both required before completion

**When to use each test type:**

| Change Type | Logic Tests | UI Tests |
|-------------|-------------|----------|
| Backend API endpoint | Required | Not needed |
| Business logic | Required | Not needed |
| Hook/utility logic | Required | Not needed |
| New UI component | Required (logic) | Required (visual) |
| Styling/layout change | Not needed | Required |
| User flow change | Required (logic) | Required (flow) |
| Bug fix (backend) | Required | Not needed |
| Bug fix (UI) | If logic involved | Required |

**Pre-Completion Verification:**

Before marking ANY milestone complete:

    # 1. Logic Tests
    [your backend test command]
    [your frontend test command]

    # 2. UI Tests (if UI changed)
    - Start dev server
    - Use Chrome extension to navigate to affected pages
    - Take screenshots, verify visual correctness
    - Test user interactions (click, type, submit)
    - Test at mobile viewport if responsive

**Requirements:**
1. Logic tests pass (no failures, no skips without rationale)
2. Coverage meets targets: [your coverage targets]
3. UI tests verify visual correctness (screenshots reviewed)
4. User flows complete successfully in browser

**Failure Handling:**

If tests don't pass:
- DO NOT mark milestone complete in Progress table
- DO NOT run Archive step of Cleanup Loop
- DO document issue in "Known Issues and Future Improvements"
- DO keep milestone "in-progress" until tests pass

**Memory Integration:**

When archiving to `.claude/memory/milestones/[feature].md`, include "Testing Approach" section:

    ## Testing Approach (MXX)

    **Logic Tests:**
    - Files: paths/to/test/files
    - Coverage: XX%
    - Key cases: list

    **UI Tests:**
    - Pages tested: /page1, /page2, etc.
    - Flows verified: flow description
    - Viewports: desktop, mobile
    - Issues found: none / list

**Verification:** Run your test commands and Chrome UI verification before any milestone completion.


---

## Completed Milestones Summary

<!-- CUSTOMIZE: Track completed milestones here -->
All milestones archived in `.claude/memory/milestones/`. Key highlights:

| Feature | Archive | Notes |
|---------|---------|-------|
| [Feature 1] | `[file].md` | [Brief description] |
| [Feature 2] | `[file].md` | [Brief description] |


### Infrastructure Deployment (Status)

<!-- CUSTOMIZE: Your infrastructure deployment details -->
Deploy [your project] from localhost to production. After completion, users can access the system from any device via the web.

**Architecture:**

    <!-- CUSTOMIZE: Draw your architecture diagram -->
    User Browser
         │
         ▼
    ┌─────────────┐
    │  [Frontend] │
    └──────┬──────┘
           │
           ▼
    ┌─────────────┐
    │  [Backend]  │
    └──────┬──────┘
           │
           ▼
    ┌─────────────┐
    │  [Database] │
    └─────────────┘

**Why [your architecture choice] (if relevant):**
- [Reason 1]
- [Reason 2]
- [Reason 3]

**Cost Estimate:** [Your cost estimate]

---

#### Credentials Reference (NEVER commit to git)

<!-- CUSTOMIZE: Your credentials reference -->
| Credential | Where to Store | How to Get |
|------------|----------------|------------|
| [Credential 1] | [Location] | [Instructions] |
| [Credential 2] | [Location] | [Instructions] |

**Backend .env template:**

    ENVIRONMENT=production
    [VAR_1]=your-value
    [VAR_2]=your-value

**Frontend Environment Variables:**

    [VITE_VAR_1]=your-value
    [VITE_VAR_2]=your-value

---

#### Operational Procedures

<!-- CUSTOMIZE: Your operational procedures -->

**Deploy Backend Updates:**

    [your deploy commands]

**Rollback Backend:**

    [your rollback commands]

**Rollback Frontend:**
[Your rollback procedure]

**View Logs:**

    [your log viewing commands]

---

#### Troubleshooting Guide

<!-- CUSTOMIZE: Common issues and solutions -->

**[Common Issue 1]:**
1. [Diagnostic step]
2. [Fix step]

**[Common Issue 2]:**
1. [Diagnostic step]
2. [Fix step]


## Tech Stack Reference

<!-- CUSTOMIZE: Your tech stack summary -->
**Full specs:** `.claude/memory/schemas/components.md`

Stack: [Your tech stack summary].
Structure: [Your project structure].
Design: [Your design system summary]. See archive for full specs.


## Research Foundation (if applicable)

<!-- CUSTOMIZE: Research/theory behind your system, or delete if not applicable -->
**Full archive:** `.claude/memory/reference/research.md`

[Summary of research/theory informing your system design.]


## Revision History

**Full changelog:** See `.claude/memory/reference/retrospective.md`

Key milestones: [Summary of major versions/releases]. All complete as of [date].

**[Date]:** [Recent significant update summary].
