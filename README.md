# POC OpenCode × Promptfoo

Minimalist POC to test OpenCode configuration (Skills, `AGENTS.md`, MCP, etc.) with [Promptfoo](https://www.promptfoo.dev/).

This POC is part of a larger effort to implement an **`agent-eval-harness`** system to rigorously develop and refine my OpenCode configuration.

Promptfoo tests an OpenCode instance that uses the configuration located in `./config/opencode/` rather than OpenCode's default global configuration in `~/.config/opencode/`.

## Prerequisites

- [Mise](https://mise.jdx.dev/) must be installed on your machine.

## Installation

```bash
$ mise install
$ pnpm install
```

## Usage

### Run tests

```bash
$ mise eval
[eval] $ promptfoo eval --no-cache
Cache is disabled.
Starting evaluation eval-Xmj-2026-05-14T09:23:18
Running 4 test cases (up to 4 at a time)...
Evaluating [████████████████████████████████████████] 100% | 4/4 | OpenCode SDK (minimax-m2.5) "Translate " language=French input=Hello world

┌───────────────────────────────────────────────────────────────────┬───────────────────────────────────────────────────────────────────┬───────────────────────────────────────────────────────────────────┬───────────────────────────────────────────────────────────────────┬───────────────────────────────────────────────────────────────────┐
│ input                                                             │ language                                                          │ sessionId                                                         │ [OpenCode SDK (minimax-m2.5)] Translate the following English     │ [OpenCode SDK (deepseek-v4-flash)] Translate the following        │
│                                                                   │                                                                   │                                                                   │ text to {{language}} using proper spelling, punctuation, and      │ English text to {{language}} using proper spelling, punctuation,  │
│                                                                   │                                                                   │                                                                   │ diacritics: {{input}}                                             │ and diacritics: {{input}}                                         │
├───────────────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────────┤
│ Hello world                                                       │ French                                                            │ ses_1da33cc52ffeSQtTq06llj1YVM                                    │ [PASS]                                                            │ [PASS] Bonjour le monde                                           │
│                                                                   │                                                                   │                                                                   │ Bonjour le monde                                                  │                                                                   │
├───────────────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────────┼───────────────────────────────────────────────────────────────────┤
│ Where is the library?                                             │ Spanish                                                           │ ses_1da33cc4bffeuRlhI3SQ29I52a                                    │ [PASS]                                                            │ [PASS] ¿Dónde está la biblioteca?                                 │
│                                                                   │                                                                   │                                                                   │ Where is the library? → **¿Dónde está la biblioteca?**            │                                                                   │
└───────────────────────────────────────────────────────────────────┴───────────────────────────────────────────────────────────────────┴───────────────────────────────────────────────────────────────────┴───────────────────────────────────────────────────────────────────┴───────────────────────────────────────────────────────────────────┘
✓ Eval complete (ID: eval-Xmj-2026-05-14T09:23:18)

» View results: promptfoo view
» Share with your team: https://promptfoo.app
» Feedback: https://promptfoo.dev/feedback

Total Tokens: 14,219
  Eval: 14,219 (10,481 prompt, 125 completion, 3,584 cached, 29 reasoning)

Results:
  ✓ 4 passed (100%)
  0 failed (0%)
  0 errors (0%)
Duration: 14s (concurrency: 4)
```

```
$ promptfoo view -n
Server running at http://localhost:15500 and monitoring for new evals.
```

### View results

```bash
$ pnpm test:ui
```
