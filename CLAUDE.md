# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a **Zettelkasten knowledge base** about governing AI agent identities at enterprise scale using Microsoft Entra Agent ID. It is a documentation-only repository with no code to build or test.

## Content Domain

The knowledge base covers:
- Microsoft Entra Agent ID (Preview)
- Non-human identity (NHI) governance
- Agent lifecycle management: registration, ownership, access control, monitoring, retirement
- Zero Trust security patterns for AI agents

## File Conventions

### Naming Pattern
Files use numeric prefixes to organize by topic:
- `000-*` — Map of Content (MOC) index file
- `100-109` — Core concepts (pets vs swarms, NHI, Entra overview)
- `110-119` — Phase 1: Registration & Discovery
- `120-129` — Phase 2: Ownership & Sponsorship
- `130-139` — Phase 3: Access Control
- `140-149` — Phase 4: Monitoring & Protection
- `150-159` — Phase 5: Retirement
- `160-169` — Implementation Patterns

### Note Structure
Each note follows this structure:
1. **Title** — H1 heading
2. **Tags** — Hashtags on line 3 (e.g., `#phase1 #registration #blueprint`)
3. **Content** — Concept explanation with tables, diagrams, lists
4. **Links section** — Related notes using wikilinks `[[note-name]]`
5. **Source section** — Microsoft Learn URLs or reference attribution

### Wikilinks
Notes connect via `[[numeric-prefix-note-slug]]` format. Always include the full filename without `.md` extension.

## Working with This Repository

When adding or editing notes:
- Follow the existing numeric prefix scheme
- Include appropriate phase/topic hashtags
- Add bidirectional wikilinks to related notes
- Include Microsoft Learn source URLs where applicable
- Use ASCII diagrams (box drawing characters) for architecture visualizations
- Tables are preferred for comparison content
