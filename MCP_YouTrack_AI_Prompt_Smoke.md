# QA SMOKE Test Generation Prompt (Critical Path Validation)

## 🚨 CRITICAL: THIS PROMPT FILE MUST BE READ COMPLETELY - NO EXCEPTIONS!

**MANDATORY REQUIREMENT:** When instructed to read this prompt file (MCP_YouTrack_AI_Prompt_Smoke.md):

- **READ THE ENTIRE FILE** - Use `Bash: cat` to read ALL content at once
- **NO PARTIAL READING** - Don't read just beginning and end
- **NO SAMPLING** - Every line contains critical instructions
- **VERIFICATION REQUIRED** - First run `wc -l` to check total lines, then confirm full reading
- **Missing ANY instruction = Task failure**

**PROPER READING APPROACH:**

1. Check file size: `wc -l MCP_YouTrack_AI_Prompt_Smoke.md`
2. Read complete file: `Bash: cat MCP_YouTrack_AI_Prompt_Smoke.md`
3. If file too large for single read, use systematic sections ensuring NO gaps
4. Document what was read and verify completeness

**📋 VERIFICATION CHECKPOINT - After reading this file, confirm:**

- [ ] Total lines read: **\_** (record actual count from `wc -l`)
- [ ] Found section: "Rapid YouTrack Data Extraction"
- [ ] Found section: "GO/NO-GO Decision Matrix"
- [ ] Found section: "P0 Smoke Test Scenarios"
- [ ] Read the COMPLETE file including END sections (not just beginning)

## 🔥 **SMOKE TEST MISSION: Verify Core Business Logic Works NOW**

### **⚡ SMOKE TEST MINDSET:**

**Primary Question:** "Is the feature broken for customers RIGHT NOW?"  
**Core Focus:** Business-critical paths + Show-stopper bugs + Revenue impact  
**Time Target:** 15-30 minutes execution maximum  
**Decision Output:** Binary GO/NO-GO (no maybes)  
**Success Metric:** 100% P0 pass = GO | Any P0 fail = NO-GO

---

## 🚨 CRITICAL WARNING: Focus on What Kills the Feature!

**SMOKE Testing is about finding SHOWSTOPPERS, not perfection:**

- **Customer can't buy** = NO-GO
- **Feature doesn't appear** = NO-GO
- **Business rule violated** = NO-GO
- **Data gets corrupted** = NO-GO
- **Small UI issues** = Ignore for now

---

## 🎯 Rapid YouTrack Data Extraction (3 Minutes STRICT)

### 1. Core Requirements Extraction (90 seconds)

**🚨 CRITICAL: Read key requirements COMPLETELY even for smoke:**

```bash
mcp_YouTrack_get_issue_raw(issue_id="TASK-ID")
```

**Extract these CRITICAL elements:**

- **Primary feature purpose** (exact feature name from task)
- **Core business rules** with SPECIFIC conditions
- **🚨 Critical exclusion rules** (scan for: "NO", "NOT", "EXCEPT", "UNLESS", "NEVER", "WITHOUT")
- **Main acceptance criteria** that define GO/NO-GO
- **Specific product/entity names** (use EXACT names from task)

**⚡ CRITICAL KEYWORD PATTERNS FOR SMOKE:**
| Keyword in Task | Smoke Test Required | Test Type |
|-----------------|-------------------|-----------|
| **"ONLY if/when"** | YES - P0 | Qualification test |
| **"NO [feature] when"** | YES - P0 | Exclusion test |
| **"MUST [action]"** | YES - P0 | Mandatory flow test |
| **"SHALL NOT"** | YES - P0 | Prohibition test |
| **"EXCEPT when"** | YES - P0 | Exception test |

### 2. Comment Intelligence Mining (60 seconds)

```bash
mcp_YouTrack_get_issue_comments(issue_id="TASK-ID")
```

**Quick extraction of:**

- **Statistical targets** that define success (e.g., "3.75% conversion target")
- **Business justification** (reveals P0 priority)
- **Critical clarifications** (e.g., "This should NOT work when...")
- **Edge cases mentioned** by stakeholders

### 3. Blocker Bug Conversion (30 seconds)

```bash
# Find ONLY blocker/critical bugs
mcp_YouTrack_advanced_search(query="caused by: TASK-ID")
mcp_YouTrack_get_issue_links(issue_id="TASK-ID")  # Check "Leads to" links
```

**Immediate bug-to-test conversion:**
| Bug Type Found | Smoke Test Priority |
|----------------|-------------------|
| Feature doesn't appear | P0 - Availability test |
| Data loss/corruption | P0 - Persistence test |
| Business rule violated | P0 - Rule enforcement test |
| Complete feature failure | P0 - Core function test |
| Critical error/crash | P0 - Stability test |

---

## 📋 SMOKE Test Decision Table (Universal Template for ANY Task)

### **🎯 RAPID TEST EXECUTION TABLE (Adapt Placeholders to Your Specific Task)**

**INSTRUCTIONS:** Replace [bracketed placeholders] with actual values from YOUR task

| ID      | Test Scenario           | Setup                                                                  | Action                                           | Expected Result                        | Pass? | Priority |
| ------- | ----------------------- | ---------------------------------------------------------------------- | ------------------------------------------------ | -------------------------------------- | ----- | -------- |
| **S01** | **Feature Available**   | [Your qualifying product/item from task] for [customer type from task] | Navigate to [feature location from requirements] | Feature [exact name from task] visible | ⬜    | 🔴 P0    |
| **S02** | **Qualification Works** | [Specific qualifying condition from your task]                         | Trigger [primary action from task]               | [Feature name] activates correctly     | ⬜    | 🔴 P0    |
| **S03** | **Exclusion Enforced**  | Add [specific exclusion item from your task]                           | Try access [feature name]                        | Feature blocked/hidden                 | ⬜    | 🔴 P0    |
| **S04** | **Data Persists**       | [Feature] active state                                                 | Refresh/navigate away                            | State maintained                       | ⬜    | 🔴 P0    |
| **S05** | **No Crash**            | Any valid state                                                        | Execute [main workflow from task]                | No errors/crashes                      | ⬜    | 🔴 P0    |
| **S06** | **Customer Type A**     | [First customer type from task]                                        | Use [feature]                                    | Works per requirements                 | ⬜    | 🟡 P1    |
| **S07** | **Customer Type B**     | [Second customer type from task]                                       | Use [feature]                                    | Works per requirements                 | ⬜    | 🟡 P1    |
| **S08** | **Error Handled**       | Invalid [data type from task]                                          | Submit/Save                                      | Appropriate error shown                | ⬜    | 🟡 P1    |
| **S09** | **State Changes**       | [Initial state from task]                                              | [State change action]                            | [New state] reached                    | ⬜    | 🟡 P1    |
| **S10** | **Loads Fast**          | Any state                                                              | Load [feature]                                   | < 5 seconds                            | ⬜    | 🟢 P2    |

**⬜ Check off as you test | ✅ Pass | ❌ Fail**

**STOP CONDITIONS:**

- **Any 🔴 P0 = ❌** → **STOP TESTING → NO-GO**
- **All 🔴 P0 = ✅** → Continue to P1
- **>2 🟡 P1 = ❌** → **NO-GO Recommendation**
- **All P0 + Most P1 = ✅** → **GO Decision**

---

## 🎯 DECISION TABLE TESTING (Universal Logic Validation)

### **🚨 MANDATORY: Create Decision Tables for Complex Logic**

**When to Use Decision Tables:**

- Feature has 3+ conditional rules (e.g., "IF this AND that BUT NOT when...")
- Multiple user types with different behaviors
- Complex qualification/exclusion logic
- Business rules with combinations of conditions
- Any feature where logic is hard to explain in words

**🚨 CRITICAL: Create SEPARATE tables for each major component/variant:**

- **Different feature types** (e.g., Component A vs Component B vs Component C)
- **Different user roles** (Admin vs User vs Guest)
- **Different business contexts** (Personal vs Organization)
- **Different product categories** (Product Type A vs Type B)

### **1. [FIRST COMPONENT NAME] - Decision Logic**

| Condition                              | TC1     | TC2     | TC3    | TC4    | TC5    | TC6     | TC7    | TC8    | TC9    | TC10   | TC11   | TC12   |
| -------------------------------------- | ------- | ------- | ------ | ------ | ------ | ------- | ------ | ------ | ------ | ------ | ------ | ------ |
| **[Primary Condition from Task]**      | Yes     | Yes     | Yes    | No     | No     | Yes     | Yes    | Yes    | Yes    | No     | Yes    | Yes    |
| **[Secondary Condition from Task]**    | Yes     | Yes     | Yes    | No     | No     | Yes     | Yes    | Yes    | Yes    | No     | No     | Yes    |
| **[Exclusion Condition from Task]**    | No      | No      | No     | Yes    | Yes    | No      | No     | No     | No     | Yes    | Yes    | No     |
| **[Customer/User Type Condition]**     | No      | No      | No     | Yes    | Yes    | No      | No     | No     | No     | Yes    | No     | No     |
| **[State/Status Condition]**           | No      | No      | No     | No     | No     | No      | No     | No     | Yes    | No     | No     | No     |
| **[Conflicting Item/Feature Present]** | No      | No      | No     | No     | No     | No      | No     | No     | No     | No     | No     | Yes    |
| **[Restriction Condition from Task]**  | No      | No      | Yes    | No     | Yes    | No      | No     | No     | No     | No     | No     | No     |
| **[Environment/Context Condition]**    | No      | Yes     | No     | No     | No     | No      | No     | No     | No     | No     | No     | No     |
| **[Permission/Access Condition]**      | Yes     | Yes     | Yes    | Yes    | Yes    | No      | Yes    | No     | Yes    | Yes    | Yes    | Yes    |
| **[Ownership/Existing State]**         | No      | No      | No     | No     | No     | No      | Yes    | No     | No     | No     | No     | No     |
| **[Business Rule Condition]**          | No      | No      | No     | No     | No     | No      | No     | Yes    | No     | No     | No     | No     |
| **[System State Condition]**           | Yes     | Yes     | Yes    | Yes    | Yes    | Yes     | Yes    | Yes    | No     | Yes    | Yes    | Yes    |
| **Expected [FIRST COMPONENT] Result**  | **YES** | **YES** | **NO** | **NO** | **NO** | **YES** | **NO** | **NO** | **NO** | **NO** | **NO** | **NO** |

**Key Test Scenarios:**

- **TC1**: [Describe test case 1 scenario] → Expected result
- **TC2**: [Describe test case 2 scenario] → Expected result
- **TC3**: [Describe test case 3 scenario] → Expected result
- **TC4**: [Describe test case 4 scenario] → Expected result
- **TC5**: [Describe test case 5 scenario] → Expected result
- **TC6**: [Describe test case 6 scenario] → Expected result
- **TC7**: [Describe test case 7 scenario] → Expected result
- **TC8**: [Describe test case 8 scenario] → Expected result
- **TC9**: [Describe test case 9 scenario] → Expected result
- **TC10**: [Describe test case 10 scenario] → Expected result
- **TC11**: [Describe test case 11 scenario] → Expected result
- **TC12**: [Describe test case 12 scenario] → Expected result

### **2. [SECOND COMPONENT NAME] - Decision Logic**

| Condition                                 | TC1     | TC2     | TC3    | TC4    | TC5    | TC6     | TC7    | TC8    | TC9    | TC10   | TC11   | TC12   |
| ----------------------------------------- | ------- | ------- | ------ | ------ | ------ | ------- | ------ | ------ | ------ | ------ | ------ | ------ |
| **[Primary Condition for Component 2]**   | Yes     | Yes     | Yes    | No     | No     | Yes     | Yes    | Yes    | Yes    | No     | Yes    | Yes    |
| **[Secondary Condition for Component 2]** | Yes     | Yes     | Yes    | No     | No     | Yes     | Yes    | Yes    | Yes    | No     | No     | Yes    |
| **[Component 2 Specific Condition]**      | No      | No      | No     | Yes    | Yes    | No      | No     | No     | No     | Yes    | Yes    | No     |
| **[Exclusion Condition for Component 2]** | No      | No      | No     | Yes    | Yes    | No      | No     | No     | No     | Yes    | No     | No     |
| **[Same conditions as Component 1...]**   | ...     | ...     | ...    | ...    | ...    | ...     | ...    | ...    | ...    | ...    | ...    | ...    |
| **Expected [SECOND COMPONENT] Result**    | **YES** | **YES** | **NO** | **NO** | **NO** | **YES** | **NO** | **NO** | **NO** | **NO** | **NO** | **NO** |

**Key Test Scenarios:**

- **TC1**: [Component 2 specific scenario] → Expected result
- **TC2**: [Component 2 specific scenario] → Expected result
- [Continue for all test cases...]

### **3. [THIRD COMPONENT NAME] - Decision Logic**

[Create additional tables as needed for complex features with multiple components]

**Instructions for Creating Decision Tables:**

1. **Identify components** - Create separate table for each major feature variant/type
2. **Replace placeholders** with actual conditions from your task
3. **Identify ALL conditions** that affect each component's behavior
4. **List ALL possible combinations** - don't skip "obvious" ones
5. **Use exact names** from task description (not generic terms)
6. **Test each column** as separate test case
7. **Document key scenarios** for each test case
8. **Follow the pattern** - Same format for all tables but different conditions per component

---

## 🔥 BUSINESS RULE DECISION MATRIX (Core Logic Validation)

### **Critical Business Rules from Task (ADAPT TO YOUR SPECIFIC TASK):**

| Business Condition         | Test 1  | Test 2 | Test 3 | Test 4 | Test 5 |
| -------------------------- | ------- | ------ | ------ | ------ | ------ |
| **Has [qualifying item]?** | Yes     | Yes    | No     | Yes    | No     |
| **Has [exclusion item]?**  | No      | Yes    | No     | No     | Yes    |
| **Customer type valid?**   | Yes     | Yes    | Yes    | No     | Yes    |
| **In valid state?**        | Yes     | Yes    | Yes    | Yes    | No     |
| **→ FEATURE SHOWS?**       | **YES** | **NO** | **NO** | **NO** | **NO** |
| **Test Result**            | ⬜      | ⬜     | ⬜     | ⬜     | ⬜     |

**Each column = one smoke test. Check ⬜ when tested.**

---

## ⚡ ULTRA-FAST SMOKE CHECKLIST (30-Second Visual Check)

### **Core Functionality Matrix:**

| Feature Aspect            | Working?     | Notes |
| ------------------------- | ------------ | ----- |
| **Appears when should**   | ⬜ Yes ⬜ No |       |
| **Hidden when shouldn't** | ⬜ Yes ⬜ No |       |
| **Main action works**     | ⬜ Yes ⬜ No |       |
| **Data saves**            | ⬜ Yes ⬜ No |       |
| **No crashes**            | ⬜ Yes ⬜ No |       |

**ALL "Yes" = GO ✅ | ANY "No" = NO-GO 🔴**

---

## 📊 SMOKE Test Result Summary Table

### **Quick GO/NO-GO Decision Matrix:**

| Test Group             | Total  | Pass   | Fail   | Result                      |
| ---------------------- | ------ | ------ | ------ | --------------------------- |
| **🔴 P0 Critical**     | \_\_\_ | \_\_\_ | \_\_\_ | **100% Pass Required**      |
| **🟡 P1 Important**    | \_\_\_ | \_\_\_ | \_\_\_ | **>75% Pass Expected**      |
| **🟢 P2 Nice-to-have** | \_\_\_ | \_\_\_ | \_\_\_ | **Ignored for GO decision** |
| **TOTAL**              | \_\_\_ | \_\_\_ | \_\_\_ | **Decision: **\_\_\_\_****  |

### **Final GO/NO-GO Decision:**

| P0 Pass Rate | P1 Pass Rate | DECISION           | Action              |
| ------------ | ------------ | ------------------ | ------------------- |
| 100%         | ≥75%         | **GO** ✅          | Ship it!            |
| 100%         | 50-74%       | **CONDITIONAL** 🟡 | Review P1 failures  |
| <100%        | Any          | **NO-GO** 🔴       | Fix P0 issues first |

---

## 🎯 Smoke Test Execution Strategy

### **Execution Order (Time-Boxed):**

```
Phase 1 (5 min): Setup test environment and data
Phase 2 (10 min): Execute P0 tests (typically 3-7 critical tests)
  ↓ If ANY P0 fails → STOP, NO-GO decision
Phase 3 (10 min): Execute P1 tests (typically 2-5 important tests)
  ↓ If majority fail → NO-GO recommendation
Phase 4 (5 min): Execute P2 tests if time permits
Phase 5 (5 min): Document results and decision
```

### **Quick Decision Matrix:**

| P0 Pass Rate | P1 Pass Rate | P2 Pass Rate | Decision           |
| ------------ | ------------ | ------------ | ------------------ |
| 100%         | >80%         | Any          | **GO** ✅          |
| 100%         | 50-80%       | Any          | **CONDITIONAL** 🟡 |
| <100%        | Any          | Any          | **NO-GO** 🔴       |

---

## 📊 Smoke Test Report Template (Short & Decisive)

```markdown
# SMOKE TEST REPORT: [TASK-ID]

**Date:** [Date] | **Build:** [Build Number] | **Duration:** [X minutes]

## 🎯 DECISION: [GO/NO-GO/CONDITIONAL]

### Test Results Summary:

| Priority | Total | Passed | Failed | Pass Rate |
| -------- | ----- | ------ | ------ | --------- |
| P0       | 5     | [X]    | [X]    | [X%]      |
| P1       | 3     | [X]    | [X]    | [X%]      |
| P2       | 2     | [X]    | [X]    | [X%]      |

### Critical Findings:

- 🔴 **Blockers:** [List any P0 failures]
- 🟡 **Risks:** [List P1 failures]
- 🟢 **Passed:** Core functionality verified

### Recommendation:

[One sentence GO/NO-GO recommendation with reason]

### Failed Tests Details (if any):

| Test ID   | Issue                 | Impact            |
| --------- | --------------------- | ----------------- |
| SMOKE-XXX | [Failure description] | [Business impact] |
```

---

## 🔥 Quick Smoke Test Patterns

### **Feature Type Quick Tests:**

#### **Authentication/Security Features**

1. Can authorized users access? → YES/NO
2. Are unauthorized users blocked? → YES/NO
3. Do permissions work? → YES/NO

#### **Payment/Transaction Features**

1. Can payment be initiated? → YES/NO
2. Is payment processed? → YES/NO
3. Is confirmation received? → YES/NO

#### **CRUD Features**

1. CREATE works? → YES/NO
2. READ works? → YES/NO
3. UPDATE works? → YES/NO
4. DELETE works? → YES/NO

#### **Integration Features**

1. External service connects? → YES/NO
2. Data flows correctly? → YES/NO
3. Errors handled? → YES/NO

---

## ⚡ Smoke Test Best Practices

### **DO:**

- ✅ Focus on customer-critical paths only
- ✅ Keep tests simple and fast
- ✅ Use existing test data
- ✅ Stop immediately on P0 failure
- ✅ Make clear GO/NO-GO decision

### **DON'T:**

- ❌ Test edge cases
- ❌ Validate all error messages
- ❌ Check all browser combinations
- ❌ Measure performance precisely
- ❌ Write detailed bug reports

### **Time Limits:**

- **Setup:** 5 minutes maximum
- **Per Test:** 2 minutes maximum
- **Total Suite:** 30 minutes maximum
- **Reporting:** 5 minutes maximum

---

## 🎯 Universal Smoke Test Checklist

For ANY feature, verify these basics:

- [ ] Feature is accessible/visible
- [ ] Primary action can be triggered
- [ ] Basic qualification rules work
- [ ] Critical exclusions are enforced
- [ ] No system crashes occur
- [ ] Data persists after actions
- [ ] Basic integrations connect
- [ ] Error states don't break system
- [ ] Different user types supported
- [ ] Core workflow completes

**If all checked → GO ✅**  
**If any critical unchecked → NO-GO 🔴**

---

## 📝 YouTrack MCP Commands for Smoke

```bash
# Essential commands only:
mcp_YouTrack_get_issue_raw(issue_id="TASK-123")         # Core requirements
mcp_YouTrack_get_issue_comments(issue_id="TASK-123")    # Critical clarifications
mcp_YouTrack_advanced_search(query="caused by: TASK-123")  # Blocker bugs
mcp_YouTrack_get_issue_links(issue_id="TASK-123")      # Related critical issues
```

---

## 🚀 SMOKE vs FULL Testing Strategy

### **When to Use This SMOKE Prompt:**

- ✅ After every deployment/build
- ✅ Before starting deep testing
- ✅ Urgent GO/NO-GO decisions
- ✅ Quick regression check
- ✅ 15-30 minute validation window

### **When to Use Full MCP_YouTrack_AI_Prompt.md:**

- ✅ New feature validation
- ✅ Complete test planning
- ✅ Edge case discovery
- ✅ 50-100+ test scenarios needed
- ✅ 2-4 hour comprehensive testing

### **The Power of Two-Prompt Strategy:**

```
SMOKE (This Prompt)         →    FULL (Parent Prompt)
==================================================
Quick validation            →    Deep validation
5-10 critical tests         →    Complete test coverage
Binary GO/NO-GO             →    Risk-based analysis
Find showstoppers only      →    Find all issues
3 min data extraction       →    Complete analysis
YouTrack essentials         →    YouTrack + Code + Full Analysis
15-30 min execution         →    2-4 hours execution
```

---

## ⚡ Final SMOKE Testing Principles

**REMEMBER: SMOKE is about SPEED and DECISION**

1. **If it's broken for customers = NO-GO** (don't overthink)
2. **If core business rules work = GO** (fix small issues later)
3. **If you need more than 30 minutes = use full prompt** (this is wrong tool)
4. **If P0 fails = STOP immediately** (don't waste time on P1/P2)

**The SMOKE Test Mantra:**

> "Does it work well enough to ship? YES or NO. Nothing else matters right now."

**SUCCESS = Fast, Clear, Actionable GO/NO-GO Decision Based on Core Business Logic**
