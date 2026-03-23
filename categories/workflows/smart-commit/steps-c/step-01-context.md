---
name: 'step-01-context'
description: 'Analyze project context, detect available scripts, and study commit conventions'

nextStepFile: './step-02-validate.md'
---

# Step 1: Context Analysis

## STEP GOAL:

To verify prerequisites (git repo with uncommitted changes), understand the project context, detect available validation scripts, and study existing commit conventions — all silently and autonomously.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:

- 🛑 NEVER generate content without completing all analysis steps
- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: When loading next step, ensure entire file is read
- 🔇 WORK SILENTLY: Do not output intermediate results — only report errors or proceed

### Role Reinforcement:

- ✅ You are a Git expert and Conventional Commits specialist
- ✅ You work autonomously and silently through analysis
- ✅ You only stop to report errors or present results
- ✅ You bring deep understanding of code change semantics

### Step-Specific Rules:

- 🎯 Focus ONLY on gathering context — do not analyze changes yet
- 🚫 FORBIDDEN to start committing or proposing commits
- 🚫 FORBIDDEN to attempt fixing any issues found
- 🔇 Work silently — no output unless an error stops the workflow

## EXECUTION PROTOCOLS:

- 🎯 Follow the MANDATORY SEQUENCE exactly
- 🔇 Store all gathered context in memory for next steps
- 📖 Auto-proceed to next step when all checks pass
- 🛑 Stop immediately and report if prerequisites fail

## CONTEXT BOUNDARIES:

- This is the first step — no prior context available
- Focus: project structure, scripts, commit history
- Limits: do NOT analyze individual file changes (that's step-03)
- Dependencies: requires git CLI and file I/O

## MANDATORY SEQUENCE

**CRITICAL:** Follow this sequence exactly. Do not skip, reorder, or improvise.

### 1. Verify Git Repository

Run `git rev-parse --is-inside-work-tree` to confirm we are in a git repository.

**If NOT a git repo:**
Stop immediately and display:
"**This is not a Git repository.** Smart Commit requires a Git repository to operate. Please navigate to a Git project and try again."
→ END WORKFLOW

### 2. Check for Uncommitted Changes

Run `git status --porcelain` to check for changes.

**If no changes detected (empty output):**
Stop immediately and display:
"**No changes to commit.** Your working tree is clean. There is nothing to commit."
→ END WORKFLOW

### 3. Detect Available Scripts

Read `package.json` (if it exists) and extract all scripts from the `scripts` section.

Identify validation-relevant scripts by looking for keys containing:
- `lint` (e.g., `lint`, `lint:fix`, `eslint`)
- `build` (e.g., `build`, `build:prod`)
- `test` (e.g., `test`, `test:unit`, `test:e2e`)
- `check` (e.g., `check`, `check:types`, `typecheck`)
- `validate` (e.g., `validate`, `verify`)

Store the list of detected scripts for step-02.

**If no package.json exists:** Note that no automated validation scripts are available — step-02 will be skipped.

### 4. Analyze Commit History

Run `git log --oneline -20` to study recent commit messages.

Identify patterns:
- Conventional Commits format used? (`feat:`, `fix:`, `chore:`, etc.)
- Scopes used? What scopes? (`feat(auth):`, `fix(ui):`)
- Language of commit messages (English, French, etc.)
- Any other conventions (ticket references, co-authors, etc.)

Store these conventions for step-03 (commit message generation).

### 5. Understand Project Structure

Analyze the project to understand its nature:
- Read key config files (package.json, tsconfig.json, etc.) to understand the tech stack
- Note the main source directories
- Understand the project type (web app, library, API, etc.)

This context helps make intelligent commit grouping decisions in step-03.

### 6. Proceed to Validation

Display: "**Proceeding to technical validation...**"

#### Menu Handling Logic:

- After all context gathered successfully, immediately load, read entire file, then execute {nextStepFile}

#### EXECUTION RULES:

- This is an auto-proceed step with no user choices
- Proceed directly to next step after context analysis
- Only stop if prerequisites fail (no git repo, no changes)

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:

- Git repository confirmed
- Uncommitted changes detected
- Available scripts identified (or absence noted)
- Commit conventions analyzed from history
- Project structure understood
- All context stored for subsequent steps
- Auto-proceeded to step-02

### ❌ SYSTEM FAILURE:

- Not checking for git repository first
- Not stopping when no changes exist
- Outputting intermediate analysis results to user
- Attempting to analyze individual file changes (too early)
- Attempting to commit or propose commits

**Master Rule:** This step gathers context silently. Stop only on errors. Proceed automatically on success.
