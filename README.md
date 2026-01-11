# Agentic Setup Examples

This repository illustrates agentic configurations for GitHub Copilot, focusing on multi-agent collaboration and automated workflows.

## Research Orchestration System

The current setup implements a sophisticated **Research Orchestrator** that manages a multi-phase research lifecycle by delegating tasks to sub-agents.

### Key Agents
-   **Orchestrator**: Manages the high-level workflow, state, and delegation. It handles task initialization, sequential execution of sub-tasks, and final consolidation.
-   **Employee**: A versatile general-purpose agent used for preliminary research, detailed task execution, and report compilation.
-   **Reviewer**: A quality-control agent focused on verification, anti-hallucination, and minor corrective edits.

### Workflow Phases
1.  **Planning**: Landscape survey (`prelim-research`) followed by a task breakdown (`plan-research`) into atomic, sequential task files.
2.  **Execution & Review**: A strict loop where the `employee` researches a specific sub-task and the `reviewer` audits the result for accuracy and citations.
3.  **Consolidation**: Merging all verified sub-reports into a single authoritative `FINAL_REPORT.md` or a structured `README_RESEARCH.md` index.

### Features
-   **Context-Aware File Passing**: Agents exchange information via file paths in a dedicated `{{taskFolder}}` to minimize context window bloat.
-   **Metadata Headers**: All research documents include optimized headers (**Keywords** & **Abstract**) for high-speed relevance judging and RAG-style searchability.
-   **Accountability**: Built-in "mission-critical" framing to encourage high integrity and verification.
