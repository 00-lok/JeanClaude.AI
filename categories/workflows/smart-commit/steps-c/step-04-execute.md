---
name: 'step-04-execute'
description: 'Execute the validated commit plan by staging and committing changes in order'
---

# Step 4: Execute Commits

## STEP GOAL:

To execute the user-validated commit plan by staging the correct files and creating each commit in the planned order, then present a final summary report.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:

- 📖 CRITICAL: Read the complete step file before taking any action
- 🎯 CRITICAL: Execute EXACTLY the plan that was validated — no modifications
- 🛑 STOP immediately if any git command fails

### Role Reinforcement:

- ✅ You are a Git expert executing a validated plan
- ✅ You are precise and methodical — no room for error
- ✅ You report results clearly after execution

### Step-Specific Rules:

- 🎯 Execute ONLY what was validated in step-03 — no changes to the plan
- 🚫 FORBIDDEN to modify any source files
- 🚫 FORBIDDEN to add files not included in the validated plan
- 🚫 FORBIDDEN to alter commit messages from the validated plan
- 🛑 If a git command fails, stop and report — do not continue

## EXECUTION PROTOCOLS:

- 🎯 Follow the MANDATORY SEQUENCE exactly
- 📋 Execute commits one by one in the planned order
- 🛑 Stop on any error and report what succeeded and what failed
- 📊 Present a final summary report

## CONTEXT BOUNDARIES:

- Available: validated commit plan from step-03
- Focus: precise execution of git add + git commit commands
- Limits: do NOT modify the plan, do NOT modify files
- Dependencies: validated commit plan from step-03

## MANDATORY SEQUENCE

**CRITICAL:** Follow this sequence exactly. Do not skip, reorder, or improvise.

### 1. Prepare for Execution

Before starting, ensure no files are currently staged:

Run `git reset HEAD` to unstage any previously staged files, ensuring a clean starting state.

### 2. Execute Each Commit

For each commit in the validated plan, in order:

**a. Stage files:**
```
git add <file1> <file2> ...
```
Stage ONLY the files listed for this specific commit.

**b. Verify staging:**
Run `git status` to confirm only the intended files are staged.

**c. Create commit:**
```
git commit -m "<validated message>"
```

Use the exact commit message from the validated plan. For messages with a body, use:
```
git commit -m "<title>" -m "<body>"
```

**d. Verify commit:**
Confirm the commit was created successfully.

**If any git command fails:**
Stop immediately and display:

"**Commit execution failed.**

**Successfully committed:** {N} of {total} commits
[List completed commits with their hashes]

**Failed at:** Commit {N+1}: `<message>`
**Error:**
```
[git error output]
```

**Your completed commits are safe.** The remaining changes are still uncommitted. Fix the issue and run `/smart-commit` again to commit the rest."

→ END WORKFLOW

### 3. Present Final Report

After all commits are executed successfully, display:

"**All commits executed successfully!**

| # | Hash | Message |
|---|------|---------|
| 1 | `abc1234` | `type(scope): description` |
| 2 | `def5678` | `type(scope): description` |
| ... | ... | ... |

**Total:** {N} commit(s) created."

→ END WORKFLOW

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:

- All commits from the validated plan executed in order
- Each commit contains exactly the files specified
- Commit messages match the validated plan exactly
- Clean staging between commits (no leftover staged files)
- Final report shows all commits with hashes
- Partial success reported clearly if execution stops mid-way

### ❌ SYSTEM FAILURE:

- Modifying the commit plan during execution
- Staging files not in the plan
- Altering commit messages
- Continuing after a git error
- Not resetting staging between commits
- Not reporting completed commits on partial failure

**Master Rule:** Execute the validated plan precisely. No improvisation. Stop on error. Report results clearly.
