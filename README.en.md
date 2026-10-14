# Cognitive Museum

**An AI-assisted personal knowledge workflow that brings saved records back into conversation as traceable evidence.**

[中文](README.md) · [Architecture](docs/architecture.md) · [Portfolio case study](docs/portfolio-case-study.md) · [Synthetic demonstration](examples/README.md)

Cognitive Museum combines an Obsidian-compatible Markdown vault with a coordinator, Xiao Zhang, and fourteen librarian role prompts. When a question depends on previous records, the workflow establishes a reading scope, reads the actual files, preserves their context, and passes an evidence packet to the relevant role.

## What the repository implements

- A portable vault scaffold and optional note templates.
- A coordinator and fourteen role prompts with clear responsibilities and stopping conditions.
- A shared retrieval and return protocol covering candidate discovery, text verification, provenance, counterexamples and missing material.
- Three request types for everyday queries, period reviews and maintenance.
- Separate states for evidence retrieval, delivery to a conversation and a verified file save.
- Project instructions, a combined reference and explicitly synthetic examples.

The implementation consists of Markdown protocols, prompts and templates. A file-capable AI host performs the actual reads. Cross-conversation dispatch and delivery depend on the host's tools and the user's direct authorisation. The fourteen roles are task modes; a task usually selects one primary librarian.

## Why it exists

Capturing new material is only part of a useful personal knowledge system. Reflection and discussion also need a path from an open question to actual stored records, and from those records back to the current conversation. This project makes that path explicit while preserving the user's control over scope and saving.

## Getting started

1. Use `vault-template/` as a new vault scaffold or a file-by-file reference; preserve existing personal files.
2. Set `${VAULT_ROOT}` to your own vault location. Configure the optional `${CAPTURE_BASKET}` only if needed.
3. Load the coordinator rules in an AI host with local file access. For a project environment, use `config/` and `project-reference/`.
4. Ask a natural question. If the scope is unclear, confirm the proposed scope before reading.

The role prompts are in Chinese. The architecture and portfolio documentation provide an English overview of the design.

## Evidence and validation

The original deployment verified 22 system files, consistency across the fourteen role prompts and their handbook, and a real read of a stored workflow test record with line-level provenance. The uploaded project reference was checked against a downloaded copy byte for byte.

Automatic cross-conversation round trips, phone synchronisation and complete period reviews across different hosts remain separate runtime acceptance checks. See [verification scope](docs/verification.md).

## Portfolio contribution

Human-led work defined the problem, conversational experience, authority boundaries and acceptance criteria. AI assistance supported source inspection, workflow proposals, rule edits and verification. The case study documents the design decisions and their practical limits.

All example records in this repository are fictional. Personal notes, private attachments, real handoff ledgers, local credentials and machine-specific configuration are kept outside the public repository.
