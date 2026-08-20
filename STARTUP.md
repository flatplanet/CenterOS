# STARTUP.md - First-Run Setup

Run this file only once, immediately after cloning the CenterOS template.

If this operating system has already been initialized, do not run this process again. Check root `LOG.md` for a first-run setup entry before proceeding.

After this setup is complete, future AI sessions should start with `BOOTSTRAP.md`, not this file.

## Purpose

This file turns the generic CenterOS template into a personalized AI operating system. It gathers a small amount of setup information, replaces identity placeholders across the repo, and leaves the system ready for normal use.

Do not ask for secrets, passwords, API keys, private addresses, or anything the user would not want stored in local Markdown files.

## Placeholder Tokens

Replace these identity tokens during first-run setup:

- `[OS_NAME]` - the user's name for this AI operating system. If the questionnaire does not collect a custom OS name, use `CenterOS`.
- `[AI_NAME]` - the AI's chosen or assigned name.
- `[AI_NICKNAME]` - the AI's short nickname.
- `[PRINCIPAL]` - the user's name.
- `[PRINCIPAL_NICKNAME]` - what the AI should call the user in normal conversation.

Keep `CenterOS` when the text refers to the public template/framework itself, not this user's personalized instance.

Do not replace double-brace scaffold tokens such as `{{WORKFLOW_NAME}}`, `{{WIKI_NAME}}`, `{{DATE}}`, or `{{TIMESTAMP}}`. Those belong to reusable workflow and wiki templates.

## Questionnaire

Before asking questions, tell the user:

```text
I’m going to ask a few setup questions so I can personalize this CenterOS install. You can answer each one as briefly or as fully as you want.
```

Ask these questions before making any changes. Ask one question at a time and wait for the user's answer before asking the next question. When asking each question, copy the full question exactly as written below, including examples. Do not shorten, summarize, paraphrase, or omit the examples.

1. What is your name?
2. What should your AI call you day to day?
3. Do you want to name your AI? If yes, what name? If not, I’ll use `CenterOS` by default.
4. What is the main purpose of this operating system? Examples: business ops, personal knowledge base, writing system, household admin, research hub.
5. How do you want the AI to communicate with you? Examples: direct, warm, terse, detailed, skeptical, creative.
6. Are there any writing rules the AI should always follow? Examples: no em dashes, no corporate fluff, match my voice.
7. Is there anything else you want me to know about you, or what you want my purpose to be?

## Setup Steps

1. Read `SOUL.md`, `PRINCIPAL.md`, `BOOTSTRAP.md`, `AGENTS.md`, `CLAUDE.md`, `SYSTEM_INDEX.md`, and `memory/CONTEXT.md`.
2. Ask the questionnaire above one question at a time. Wait for the user's answer after each question before continuing to the next question. Copy each question exactly, including examples.
3. Summarize the exact placeholder replacements you intend to make and wait for confirmation.
4. Replace identity placeholders across Markdown files in this repo, except inside `.obsidian/` if that directory exists.
5. Populate `SOUL.md` with the AI name, AI nickname, OS name (default `CenterOS` unless the user explicitly provided another name), principal name, principal nickname, purpose, disposition, responsibilities, and production writing rules.
6. Populate `PRINCIPAL.md` with the user's identity, work/life areas, operating preferences, and collaboration style. Leave unknown sections marked clearly as empty rather than guessing.
7. Update `SYSTEM_INDEX.md` where it describes this specific cloned instance. Leave `README.md` empty unless the user asks to create public GitHub-facing copy.
8. Search for unresolved identity placeholder tokens in Markdown files and report any that intentionally remain. Ignore double-brace scaffold tokens such as `{{WORKFLOW_NAME}}` and `{{WIKI_NAME}}`.
9. Append a `modified` entry to root `LOG.md` stating that first-run setup was completed.
10. Read `BOOTSTRAP.md` and load its operating context. Do not send the normal bootstrap greeting yet; continue to the startup completion message below.
11. Tell the user:

```text
Startup complete. [OS_NAME] is installed and ready to use.

To begin future sessions, tell me to read `BOOTSTRAP.md` and follow its instructions.

Would you like to create your first workflow? Just describe what you want it to do and I'll create it!
```

## Rules

- Run once only.
- Do not guess. Ask when an answer is needed.
- Do not store secrets or credentials.
- Do not modify files in `.obsidian/`.
- Keep paths relative to the repo root in all file content.
- Preserve CenterOS as the template/framework name unless the sentence is clearly about the user's personalized operating system.
- After startup, use `BOOTSTRAP.md` for every normal session.
