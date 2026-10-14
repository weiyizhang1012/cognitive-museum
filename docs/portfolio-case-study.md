# Portfolio case study

## Problem

The original personal knowledge workflow had a clear way to capture and save material. When the user wanted to review or discuss earlier experiences, the workflow could fall back to conversational memory or ask the user to supply candidate notes. Existing librarian prompts described the evidence they needed, but the system lacked a complete path for finding that evidence and returning it to the original discussion.

## Human-led product decisions

- Keep a natural conversational entrance rather than making the user select roles and paths.
- Treat lived experience, uncertainty and unfinished ideas as valid records.
- Require actual Markdown evidence for claims about earlier records.
- Keep reading scope, cross-conversation delivery and file saving as separate authorities.
- Reuse the existing fourteen role definitions, selecting the relevant role per task.

## AI-assisted implementation

The work began with a read-only inspection of the coordinator, system guide, workbench, collaboration protocol and role handbook. The implementation then updated the actual local authority files, added a common retrieval/return protocol, connected all fourteen role prompts to its evidence format, regenerated the handbook and updated the project configuration.

Existing system files were backed up before deployment. The original personal holdings remained outside the update set. A small real-file validation used an existing workflow test record, not a personal diary.

## Design decisions

| Decision | Reason | Trade-off |
|---|---|---|
| Plain Markdown authority files | Keep the system inspectable and portable | Runtime tools must come from the host |
| One common evidence packet | Preserve provenance between roles and conversations | Requires explicit source and coverage fields |
| One primary role by default | Reduce duplicate work and user-facing complexity | Additional analysis needs a clear new purpose |
| Query and save states separated | Let discussion finish without producing more files | Query tracking stays in the conversation |
| Explicit pending delivery state | Prevent an unverified channel from appearing complete | Some hosts need one manual backend trigger |

## What was demonstrated

The deployment verified the actual rule files, fourteen-role handbook consistency, a real stored-record read with source positions, and a byte-identical uploaded reference. It established a reusable workflow specification with a live local deployment.

Automatic cross-conversation round trips and phone synchronisation were not demonstrated. The public examples are synthetic and illustrate the workflow rather than claiming additional live tests or measured productivity gains.

## Portfolio scope

This project demonstrates human-directed, AI-assisted workflow engineering: problem diagnosis, authority design, context and evidence handling, prompt coordination, reversible changes and truthful verification. The public release contains the reusable system layer; the private knowledge collection remains private.
