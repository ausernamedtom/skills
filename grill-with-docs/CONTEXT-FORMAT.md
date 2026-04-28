# CONTEXT.md Format Guide

## Purpose
This document defines a standardized template for creating domain-specific context files in software projects, ensuring consistent terminology and clear relationships between concepts.

## Core Structure

A CONTEXT.md file should include:

- **Header**: Context name and brief description (1-2 sentences)
- **Language section**: Defines key terms with definitions and aliases to avoid
- **Relationships section**: Documents how terms connect using cardinality notation
- **Example dialogue**: Shows a dev-domain expert conversation demonstrating natural term usage
- **Flagged ambiguities**: Highlights and resolves conflicting term usage

## Key Principles

1. **Opinionated terminology** — Select the best term for each concept; list alternatives under "_Avoid_"
2. **Tight definitions** — One sentence maximum describing what something *is*
3. **Relationship mapping** — Use bold formatting and explicit cardinality (one-to-many, etc.)
4. **Context-specific only** — Exclude general programming concepts unless unique to the project
5. **Strategic grouping** — Organize terms under subheadings when natural clusters exist

## Repository Patterns

**Single-context repos**: One `CONTEXT.md` at root

**Multi-context repos**: Use `CONTEXT-MAP.md` at root listing all contexts, their locations, and inter-context relationships with event/type flows

The skill automatically detects which pattern applies based on file presence and structure.
