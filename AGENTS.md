# AGENTS.md

**Grok Build Agent Coding Rules**  
**Lightweight Karpathy/Linux/Hermes Hybrid**  
**For Small-Scale Experimental and Research Projects**

**Date:** 2026-05-27  

**Purpose:** These rules provide a lightweight, minimal framework governing all AI-assisted coding, refactoring, planning, and development tasks within Grok Build. They constitute a deliberate hybrid of Andrej Karpathy’s LLM coding principles, Linux kernel development discipline, and Hermes-inspired persistent project state tracking. The rules are specifically tailored for small-scale experimental and research projects, where they enforce simplicity, transparency, backward compatibility, and auditable continuity while preventing common AI pitfalls such as hidden errors or fabricated outputs. All agents must adhere to them strictly.

## Core Rules

### 1. Surface Assumptions and Uncertainty Explicitly
Before implementing any change, explicitly state all key assumptions. If the request is ambiguous or admits multiple interpretations, present the options or seek clarification rather than guessing. Never proceed with unverified interpretations.

### 2. Let Real Errors Propagate (No Hiding Failures)
Write code that allows genuine errors (e.g., missing files, invalid inputs, network failures, or external issues) to surface naturally. Do not introduce broad `try/except` blocks, default fallbacks, fabricated data, or other mechanisms that conceal root causes unless the user explicitly requests resilience or error-handling features for that specific case.

### 3. Never Break Userspace
Treat backward compatibility as a first-class constraint. Do not introduce breaking changes to existing interfaces, APIs, user-visible behaviors, or downstream dependencies without explicit discussion and provision of migration guidance.

### 4. Smallest Viable Change + Preserve Existing Patterns
Make only the minimal change necessary to fulfill the stated requirement. Strictly match the existing code style, structure, and conventions. Do not refactor unrelated code or add speculative features, abstractions, or configurability.

### 5. Verifiable Goals Over Vague Intent
For any non-trivial task, first rephrase the request into concrete, testable success criteria or a short plan with explicit verification checkpoints before writing significant code.

### 6. Persistent Project State Log
Maintain `PROJECT_PROGRESS.md` in the project root as the single, authoritative, high-level project state file. This file must remain extremely concise and must **never** contain full conversation history, chat transcripts, or detailed logs.

All historical records must be appended to a separate archive file: `archive/project_archive_log.md` (create the `archive/` directory if it does not exist).

`PROJECT_PROGRESS.md` must contain **only** the following sections (use Markdown headings or bullets; keep the entire file under 50 lines):

- **Project Description**: One single sentence describing the project.
- **Aiming Structure**: High-level project structure, goals, or target architecture (concise bullet points or paragraphs).
- **Current Progress Status**: One-sentence summary of what has been achieved.
- **Recent 3 Decisions**: Bullet list of the most recent three key decisions (including any explicitly surfaced assumptions).
- **Open Items**: Bullet list of ongoing works.

Update `PROJECT_PROGRESS.md` **only** at the end of a major task, after reaching a significant decision point, or upon completion of a non-trivial response involving code changes or planning. Do **not** update after every minor exchange.
At each update, append old progress status, recent decisions and reasons to `archive/project_archive_log.md` before rewriting the concise `PROJECT_PROGRESS.md`.

At the beginning of any new session or when chat context is insufficient, read `PROJECT_PROGRESS.md` first and treat it as the single source of truth. Do not rely on full workspace scans or chat context when this log exists and is up to date.


## Additional Principles
- Generate minimal code that directly addresses the requirement; prefer simple functions and existing structures over unnecessary classes or abstractions.
- Address the root cause directly; never use workarounds unless explicitly requested.
- Talk is cheap: prefer delivering working minimal code early on straightforward tasks.

These rules take precedence over any conflicting instructions in chat context unless the user explicitly overrides them.