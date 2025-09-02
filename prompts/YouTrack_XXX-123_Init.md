# QA Task Analysis: XXX-123

## Task Specification

**Target:** Create comprehensive QA test scenarios for **XXX-123** task

**Resources:**

- **YouTrack Task:** XXX-123 (complete analysis required)
- **Code Files:** QA/XXX-123/XXX-123-banner.patch

## Execution Approach

1. **Load Master Methodology:** `Bash: cat MCP_YouTrack_AI_Prompt.md`
2. **Execute Complete Analysis:** Follow all sections from master methodology
3. **Apply All 8 QA Techniques:** With verification checklists per methodology
4. **Integrate All Sources:** YouTrack (task description + task comments + task related bugs) + Code

## Critical Reminders

- **File Reading:** MANDATORY `Bash: cat` for files >100 lines + verify file size with `wc -l`
- **Patch Analysis:** Count all modified files with `grep -c "^diff --git" PATCH_FILE` and analyze ALL
- **Verification Matrix:** Complete MANDATORY audit checkpoint before delivery
- **Quality Standard:** Professional QA deliverable with 67+ test scenarios (not 20+)
- **Zero-Failure Protocol:** If any verification fails, restart from failed checkpoint

## 🔒 MANDATORY VERIFICATION BEFORE DELIVERY

**EXECUTE systematically - NO SHORTCUTS ALLOWED:**

### Pre-Analysis Verification

```bash
wc -l QA/{TASK-ID}/{TASK-ID}-banner.patch     # Verify patch size
grep -c "^diff --git" QA/{TASK-ID}/*.patch    # Count modified files
wc -l MCP_YouTrack_AI_Prompt.md               # Record methodology file size
```

### Post-Analysis Completeness Audit

- [ ] **Patch Analysis**: Read complete patch file with `cat` (not truncated Read tool)
- [ ] **File Coverage**: Analyzed ALL modified files (count verified with grep)
- [ ] **Business Logic**: Found ALL qualification functions and business rules
- [ ] **QA Techniques**: Applied ALL 8 techniques with verification checklists
- [ ] **Audit Matrix**: Completed mandatory verification matrix in methodology

**CRITICAL:** If ANY item unchecked → **Analysis incomplete** → Must restart from failure point

## Deliverable

**Output:** `QA/{TASK-ID}/{TASK-ID}-test-scenarios.md`
**Success Criteria:** All methodology requirements satisfied + audit checkpoint completed
