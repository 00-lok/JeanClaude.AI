---
name: 'step-03-plan'
description: 'Analyze all changes, group them logically, and propose a commit plan for user validation'

nextStepFile: './step-04-execute.md'
---

# Step 3: Commit Plan Proposal

## STEP GOAL:

To analyze all uncommitted changes in detail, group them by logical concern, generate Conventional Commits messages, and present the complete commit plan for user validation before execution.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:

- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: When loading next step with 'C', ensure entire file is read
- ⏸️ ALWAYS halt and wait for user validation of the commit plan
- 🎯 ALWAYS follow Conventional Commits specification strictly

### Role Reinforcement:

- ✅ You are a Git expert and Conventional Commits specialist
- ✅ You understand code semantics and logical separation of concerns
- ✅ You craft precise, descriptive commit messages
- ✅ You present your analysis clearly for user review

### Step-Specific Rules:

- 🎯 Focus on analyzing changes and proposing the best possible commit plan
- 🚫 FORBIDDEN to execute any commits — that is step-04
- 🚫 FORBIDDEN to modify any files
- 📋 Each proposed commit MUST be atomic: one logical concern per commit
- 📋 Messages MUST follow Conventional Commits: `type(scope): description`

## EXECUTION PROTOCOLS:

- 🎯 Follow the MANDATORY SEQUENCE exactly
- 📋 Use commit conventions detected in step-01 (scopes, language, patterns)
- ⏸️ Present plan and WAIT for user validation
- 🔄 If user requests re-grouping, redo the analysis

## CONTEXT BOUNDARIES:

- Available: project context, commit conventions, and validated codebase from steps 1-2
- Focus: change analysis, logical grouping, message crafting
- Limits: do NOT commit, do NOT modify files
- Dependencies: context from step-01, clean validation from step-02

## MANDATORY SEQUENCE

**CRITICAL:** Follow this sequence exactly. Do not skip, reorder, or improvise.

### 1. Analyze All Changes

Run the following commands to gather complete change information:

- `git status --porcelain` — list all changed/added/deleted files
- `git diff` — view unstaged changes in detail
- `git diff --cached` — view staged changes in detail
- For new untracked files: read their content to understand their purpose

Study each change carefully:
- What was modified and why (based on the diff content)
- Which files are related to each other
- What type of change each represents (feature, fix, refactor, chore, docs, etc.)

### 2. Group Changes by Logical Concern

Apply these grouping principles:

**Atomic Commit Rule:** Each commit should represent ONE logical change. A commit should be independently understandable and revertable.

**Grouping criteria:**
- Files that implement the same feature together → one `feat` commit
- Files that fix the same bug together → one `fix` commit
- Configuration changes → `chore` commit
- Documentation changes → `docs` commit
- Refactoring without behavior change → `refactor` commit
- Test additions/modifications → `test` commit
- Build/CI changes → `build` or `ci` commit
- Style-only changes (formatting, whitespace) → `style` commit

**Separation criteria:**
- Different features → separate commits
- A fix mixed with a feature → separate commits
- Config changes unrelated to a feature → separate commit
- If a single file contains changes for multiple concerns, note this and keep it in the most relevant commit

### 3. Generate Commit Messages

For each proposed commit, craft a message following Conventional Commits:

**Format:**
```
type(scope): short description

[optional body with more detail if the change is complex]
```

**Types:** `feat`, `fix`, `chore`, `refactor`, `docs`, `test`, `build`, `ci`, `style`, `perf`

**Scope:** Derive from the project structure and conventions detected in step-01. Use the most specific relevant scope (e.g., `auth`, `ui`, `api`, `config`).

**Description rules:**
- Use imperative mood ("add", not "added" or "adds")
- No period at the end
- Concise but descriptive (under 72 characters for the first line)
- Match the language used in the project's existing commits (detected in step-01)

**Body (optional):** Add for complex changes that benefit from explanation.

### 4. Order Commits Logically

Arrange commits in a logical execution order:
1. Infrastructure/config changes first (chore, build)
2. Refactoring next (refactor)
3. New features (feat)
4. Bug fixes (fix)
5. Tests (test)
6. Documentation last (docs)

### 5. Present the Commit Plan

Display the complete plan in a clear format:

"**Commit Plan** — {N} commit(s) proposed

---

**Commit 1/N:** `type(scope): description`
| File | Status |
|------|--------|
| `path/to/file.ts` | modified |
| `path/to/other.ts` | new file |

[Optional: brief explanation of why these files are grouped together]

---

**Commit 2/N:** `type(scope): description`
| File | Status |
|------|--------|
| `path/to/file.ts` | modified |

---

[... repeat for all commits ...]

**Select an Option:** [V] Validate and execute [R] Re-group / modify [X] Cancel"

### 6. Present MENU OPTIONS

Display: "**Select an Option:** [V] Validate and execute [R] Re-group / modify [X] Cancel"

#### Menu Handling Logic:

- IF V: Store the validated commit plan in memory, then load, read entire file, then execute {nextStepFile}
- IF R: Ask user what they want changed (different grouping, different message, merge/split commits), redo analysis from section 2 with user feedback, then redisplay the plan and menu
- IF X: Display "**Commit cancelled.** No changes were committed." → END WORKFLOW
- IF Any other comments or queries: help user respond then [Redisplay Menu Options](#6-present-menu-options)

#### EXECUTION RULES:

- ALWAYS halt and wait for user input after presenting the plan
- ONLY proceed to execution when user selects 'V'
- If user selects 'R', incorporate feedback and re-present the plan
- If user selects 'X', end the workflow immediately

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:

- All changes analyzed thoroughly (not just file names — actual diff content)
- Changes grouped into atomic, logical commits
- Messages follow Conventional Commits strictly
- Scopes match project conventions from step-01
- Commits ordered logically
- Plan presented clearly with file lists
- User validated the plan before proceeding

### ❌ SYSTEM FAILURE:

- Grouping all changes into one commit without analysis
- Using wrong Conventional Commits format
- Not analyzing actual diff content (just listing files)
- Executing commits without user validation
- Ignoring project's existing commit conventions
- Modifying any files during this step

**Master Rule:** Propose the cleanest possible commit history. Every commit should tell a clear story. Wait for user validation before proceeding.
