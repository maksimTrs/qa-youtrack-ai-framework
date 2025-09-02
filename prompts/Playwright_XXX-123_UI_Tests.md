# UI Implemented Functionality for Related Task via Playwright MCP

## Task Context & Objective

I'm providing Playwright MCP browser scenarios for task **XXX-123** to give you hands-on context of the actual UI implementation.
You have access to the test scenarios file at **QA/XXX-123/XXX-123-test-scenarios.md** and previous analysis from our conversation.

## What I'm sending:

- **Working Playwright scenarios** demonstrating the live UI implementation
- **Real test cases** showing expected behavior
- **UI workflows** that implement the task requirements

## Your objectives:

- **Execute and analyze** the provided Playwright scenarios step by step
- **Map UI behavior** to business logic and functional requirements
- **Document critical discoveries** like banner priority logic, SKU transformations, and exact UI messages
- **Update QA/XXX-123/XXX-123-test-scenarios.md** if you discover missing test cases or requirement clarifications
- **Understand** how the UI implementation reveals deeper task requirements

## Expected outcome:

A comprehensive understanding of **XXX-123** functionality based on real UI behavior, with updated test documentation containing:

- **Banner priority hierarchy** validation
- **Live SKU transformation mappings**
- **Exact success message validation points**
- **Critical edge cases** discovered through live testing

## Playwright Browser Scenarios - execute **EACH** scenario:

### Test data:

- **${{url_0}}** = https://example-test-site.com/login
- **${{email}}** = test.user@example.com
- **${{password}}** = [test_password]
- **${{url}}** = https://example-test-site.com/licenses

### Common steps as initial part - execute once:

1. **Open** ${{url_0}}
2. **Click** on "Continue with email" button
3. **Fill** email: ${{email}} and click "Continue" button
4. **Fill** password: ${{password}} and click "Log In" button

---

### Scenario - All Products Pack banner verification for organization customer type:

5. **On the new** ${{url}} page click "Buy commercial license" **OR** if you can't find it, use buttons: "Buy New License" -> "For my company"
6. **Choose** "CLion" product (it is not .NET IDE product) and click "Go to checkout"
7. **Observe** "All Products Pack" banner section (text, design, buttons, links, etc.)
8. **Click** on "All Products Pack" banner "Get it all" button
9. **Observe** new state of the banner with "Swap back to CLion" button (text, design, buttons, links, etc.)
10. **Click** on "Swap back to CLion" button
11. **In** "Subscription Pack" field choose "New Monthly" option (by default it was Annual option) and execute steps 7-10

---

### Scenario - dotUltimate banner verification for organization customer type:

5. **On the new** ${{url}} page click "Buy commercial license" **OR** if you can't find it, use buttons: "Buy New License" -> "For my company"
6. **Choose** "Rider" product (it is .NET IDE product) and click "Go to checkout"
7. **Observe** "dotUltimate" banner section (text, design, buttons, links, etc.)
8. **Click** on "dotUltimate" banner "Get dotUltimate" button
9. **Observe** new state of the banner with "Swap back to Rider" button (text, design, buttons, links, etc.)
10. **Click** on "Swap back to Rider" button
11. **In** "Subscription Pack" field choose "New Monthly" option (by default it was Annual option) and execute steps 7-10

---

### Scenario - AI banner verification for organization customer type:

5. **On the new** ${{url}} page click "Buy commercial license" **OR** if you can't find it, use buttons: "Buy New License" -> "For my company"
6. **Choose** "IntelliJ IDEA Ultimate" and "ReSharper" products and click "Go to checkout"
7. **Observe** "JetBrains AI" banner section (text, design, buttons, links, etc.)
8. **Click** on "Add to cart" banner button
9. **Observe** new product row in the cart: "JetBrains AI Pro", banner is hidden now
10. **Click** on "×" button for the "JetBrains AI Pro" product - you can see "JetBrains AI" banner again

**NOTE:** This scenario validates that **multiple IDEs trigger AI banner** (priority logic discovery)

---

### Scenario - AI banner exclusion with existing AI products:

5. **On the new** ${{url}} page click "Buy commercial license" **OR** if you can't find it, use buttons: "Buy New License" -> "For my company"
6. **Choose** "IntelliJ IDEA Ultimate" and "ReSharper" products
7. **Click** on "Team Tools & Services" tab and choose "JetBrains AI Pro"
8. **Click** "Go to checkout"
9. **Observe** "JetBrains AI" banner - banner is not here at all (exclusion logic validation)
10. **Click** on "×" button for the "JetBrains AI Pro" product - you can see "JetBrains AI" banner appear

**NOTE:** This scenario validates the **AI product exclusion rule** - no AI banner when AI product already in cart

---

> **📝 NOTE:** The same logic of the Browser Scenarios above also work for the personal customer type.
