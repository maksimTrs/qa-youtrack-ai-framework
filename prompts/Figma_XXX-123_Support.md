# Figma Frame Analysis Support for XXX-123

## 🚨 MANDATORY METHODOLOGY REFERENCE

**BEFORE starting Figma analysis, you MUST read and follow:**

- **Master QA Methodology:** `MCP_YouTrack_AI_Prompt.md` (complete file)
- **Figma Integration Section:** Section 2 - "Figma MCP Integration (OPTIONAL ENHANCEMENT MODULE)"
- **Analysis Requirements:** All 4 MCP tools × ALL frames = N×4 total tool calls

**Key Requirements from Master Methodology:**

- Use ALL 4 Figma MCP tools for EVERY frame (no selective analysis)
- Integrate findings into existing QA/XXX-123/XXX-123-test-scenarios.md file
- Follow cross-source validation approach (YouTrack ↔ Code ↔ Figma)
- Complete Figma verification matrix in master methodology audit

## Task Context & Objective

I'm providing Figma frame analysis for task **XXX-123** to give you visual design context of the UI requirements and specifications.
You have access to the test scenarios file at **QA/XXX-123/XXX-123-test-scenarios.md** and previous analysis from our conversation.

## What I'm sending:

- **8 Figma design frames** showing different banner states and customer scenarios
- **Visual specifications** for UI implementation requirements
- **Design variations** across different product types and subscription models

## Your objectives:

- **Analyze all 8 Figma frames** to understand visual requirements and design specifications
- **Map design elements** to functional requirements and business logic
- **Cross-reference with code implementation** and UI test scenarios for comprehensive coverage
- **UPDATE the existing QA/XXX-123/XXX-123-test-scenarios.md** file by integrating visual test cases directly into the existing document
- **Do NOT create separate visual analysis files** - all findings should be integrated into the main test scenarios document

## Expected outcome:

**UPDATED QA/XXX-123/XXX-123-test-scenarios.md** with integrated visual test cases, design validation requirements, and UI-specific scenarios added to existing sections. The main test scenarios document should be enhanced with visual findings, not supplemented with separate files.

## Figma Frame Analysis (Complete ALL)

1. [ ] Personal .NET → DUL: https://www.figma.com/design/1
2. [ ] Personal non-.NET → ALL: https://www.figma.com/design/2
3. [ ] Complex cart (before): https://www.figma.com/design/3
4. [ ] Complex cart (after): https://www.figma.com/design/4
5. [ ] Personal Monthly: https://www.figma.com/design/5
6. [ ] Organization Annual: https://www.figma.com/design/6
7. [ ] Organization Monthly: https://www.figma.com/design/7
8. [ ] Error states: https://www.figma.com/design/8

## Analysis Requirements (Per Master Methodology)

- **Complete Coverage:** All 8 frames × 4 MCP tools = 32 total MCP calls required
- **Integration:** Visual test cases must be integrated directly into existing QA/XXX-123/XXX-123-test-scenarios.md file
- **Enhancement, Not Replacement:** Add visual test scenarios to existing sections (e.g., add VTC-XXX test cases to existing framework)
- **Verification:** Complete Figma coverage checkpoint in master methodology audit section
- **Cross-Source Validation:** Ensure Figma findings align with YouTrack requirements and Code implementation

## Integration Approach

**DO NOT create new files.** Instead:

1. Add visual test cases to existing QA technique sections in the main document
2. Enhance existing test cases with visual validation checkpoints
3. Add design-specific scenarios to appropriate priority levels (P0/P1/P2)
4. Include visual regression prevention in existing test execution guide
