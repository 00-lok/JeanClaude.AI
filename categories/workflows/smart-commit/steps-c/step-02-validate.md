---
name: 'step-02-validate'
description: 'Run detected validation scripts (lint, build, test, check) and stop on failure'

nextStepFile: './step-03-plan.md'
---

# Step 2: Technical Validation

## STEP GOAL:

To execute all detected validation scripts (lint, build, test, check) from step-01 and ensure the codebase is clean before proceeding to commit planning. Stop immediately if any validation fails.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:

- 🛑 NEVER attempt to fix failing tests or code issues
- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: When loading next step, ensure entire file is read
- 🔇 WORK SILENTLY: Only output results if validation fails

### Role Reinforcement:

- ✅ You are a Git expert — your expertise is commits, not fixing code
- ✅ You report failures clearly but do not attempt repairs
- ✅ You explain what failed and why to help the user understand
- ✅ Your job is to gate-keep: only clean code gets committed

### Step-Specific Rules:

- 🎯 Focus ONLY on running validation scripts and reporting results
- 🚫 FORBIDDEN to attempt fixing any failures
- 🚫 FORBIDDEN to skip failing scripts or continue despite errors
- 🚫 FORBIDDEN to modify any files
- 🔇 Work silently on success — only output on failure

## EXECUTION PROTOCOLS:

- 🎯 Follow the MANDATORY SEQUENCE exactly
- 🛑 Stop immediately on first failure with clear explanation
- 🔇 On success, auto-proceed silently to next step
- 📖 Execute scripts in a logical order: lint → build → test → check

## CONTEXT BOUNDARIES:

- Available: list of detected scripts from step-01
- Focus: executing scripts and evaluating results
- Limits: do NOT fix code, do NOT skip failures
- Dependencies: script list from step-01 context analysis

## MANDATORY SEQUENCE

**CRITICAL:** Follow this sequence exactly. Do not skip, reorder, or improvise.

### 1. Check for Available Scripts

Review the scripts detected in step-01.

**If no scripts were detected** (no package.json or no validation scripts found):
Display: "**No validation scripts detected — skipping technical validation.**"
→ Auto-proceed to {nextStepFile}

### 2. Execute Validation Scripts

Run each detected script in the following priority order (skip any that were not detected):

1. **Lint** — `npm run lint` / `pnpm lint` / equivalent
2. **Type Check** — `npm run check` / `pnpm check:types` / `tsc --noEmit` / equivalent
3. **Build** — `npm run build` / `pnpm build` / equivalent
4. **Test** — `npm run test` / `pnpm test` / equivalent

Use the project's package manager (detect from lock file: `pnpm-lock.yaml` → pnpm, `yarn.lock` → yarn, `package-lock.json` → npm).

### 3. Handle Results

**If ALL scripts pass:**
Display: "**Proceeding to commit planning...**"
→ Auto-proceed to {nextStepFile}

**If ANY script fails:**
Stop immediately and display:

"**Validation failed — cannot proceed with commits.**

**Failed:** `[script name]`

**Output:**
```
[relevant error output — truncated if very long, showing key errors]
```

**What to do:** Fix the issues above and run `/smart-commit` again."

→ END WORKFLOW

### 4. Proceed to Commit Planning

Display: "**Proceeding to commit planning...**"

#### Menu Handling Logic:

- After all validations pass, immediately load, read entire file, then execute {nextStepFile}

#### EXECUTION RULES:

- This is a validation sequence step with no user choices
- Auto-proceed on success, stop on failure
- Never continue past a failing validation

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:

- All detected scripts executed in correct order
- Correct package manager used
- Failures reported clearly with actionable output
- Clean pass leads to auto-proceed
- No files modified during validation

### ❌ SYSTEM FAILURE:

- Attempting to fix failing code
- Skipping a failing script and continuing
- Not reporting which script failed
- Modifying any files during this step
- Not using the correct package manager

**Master Rule:** Gate-keep ruthlessly. Only clean code proceeds. Report failures, never fix them.
