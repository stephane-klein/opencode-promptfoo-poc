# AGENTS.md

## Project Purpose

This project implements a Proof of Concept (POC) to test with Promptfoo how OpenCode behaves with:

- SKILL.md files
- AGENTS.md files
- MCP (Model Context Protocol)
- Different types of LLMs

These tests are conducted in the context of using OpenCode Go.

The ultimate goal is to use this architecture to develop and refine an OpenCode configuration with more control and rigor, following a Test Driven Development (TDD) approach.

## Language Policy

All project documentation, code comments, and textual content must be written in **English**.

## Project Architecture

This POC is part of a larger effort to implement an **`agent-eval-harness`** system to rigorously develop and refine OpenCode configurations.

Promptfoo tests an OpenCode instance that uses the configuration located in `./config/opencode/` rather than OpenCode's default global configuration in `~/.config/opencode/`.

## Tools Used

This project uses:

- [Mise](https://mise.jdx.dev/) for tool management
- pnpm for package management
- [Jujutsu](https://github.com/martinvonz/jj) for version control
