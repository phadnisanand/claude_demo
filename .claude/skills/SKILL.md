---
name: code-reviewer
description: Automated technical review checklist for pulling and merging code.
---

# Skill Instructions
When this skill is executed, you must strictly follow this workflow before approving any code changes:

1. **Read Affected Files:** Inspect all modified or newly introduced code files.
2. **Security & Performance Audit:** Check for any clear security vulnerabilities (e.g., hardcoded credentials) or performance bottlenecks.
3. **Style Match:** Ensure code adheres to the project's formatting conventions.
4. **Generate Report:** Output a concise markdown report with:
   - ✅ Passed checks
   - ⚠️ Warnings/Suggestions
   - ❌ Critical bugs to fix
