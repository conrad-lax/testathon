# 🧪 Testathon — Let’s Win This!

Welcome to our **Testathon Challenge**!  
Your mission: **find bugs, write tests, and help us win** 🏆  

---

## 🎯 Objective

We’re testing the following website:

👉 **[OrangeHRM Demo Site](https://opensource-demo.orangehrmlive.com/web/index.php/auth/login)**

You’ll find valid **login credentials** printed on the login page (since this is a public demo site).  
Your goal is to:

- Explore the app thoroughly.  
- Create **test cases** (manual and automated).  
- **Report bugs** clearly and accurately.

---

## 🧰 Tools to Highlight

During this Testathon, we’ll be showcasing:

- **Playwright** – for automated browser testing  
- **Playwright MCP** – for AI-assisted test case generation and execution  

⚙️ Keep the tests limited to **Chromium** for simplicity and consistency.

---

## 🧪 What You’ll Do

1. **Navigate** through the OrangeHRM website.  
2. **Identify** bugs and potential issues.
3. **KINTSUGI** follow the testing strategy in kintsugi.md, with results written in a file, each with filename format "XX_{strategy_step_name}.md" (e.g., 03_negative_noise_testing.md, 04_targeted_exploration.md), with the ff. details:
    - Know Context: short Context Card (1 paragraph) + top-3 critical flows
    - Instrument & Observe: 
        - Use Playwright to navigate the page
        - Observe console in dev tool during actions
        - Observe endpoints in dev tool -> Networks tab if requests are appropriately sent with their required use case (e.g., edits should have PUT endpoint calls to a server)
        - Observe overall functionalities and flow-of-action if they match the displayed strings in the Web UI elements
        - **Quality Guidelines for Observation:**
            - Record environment details (browser, OS) for all observations
            - Document performance metrics during navigation
            - Capture screenshots or evidence for unexpected behaviors
            - Note any accessibility issues or console errors
    - [Negative & noise, Targeted exploration, Simulate real users, Utilize chaos] Make test cases using Context card from Know Context and add focus on the Instrument & Observe items for the following Principles:
        - **Negative & Noise**
            - Quality Guidelines: Create clear, step-by-step instructions with realistic test data
            - Test invalid inputs, boundary conditions, and error scenarios
            - Document expected vs actual results with business impact assessment
        - **Targeted Exploration**
            - Quality Guidelines: Focus on critical business flows with estimated execution time
            - Include prerequisites and environment setup requirements
            - Provide detailed reproduction steps for any issues found
        - **Simulate Real Users**
            - Quality Guidelines: Create test cases that QA team can easily understand and execute
            - Include realistic user scenarios and workflows
            - Document user experience issues and usability concerns
        - **Utilize Chaos**
            - Quality Guidelines: Test edge cases with proper risk assessment
            - Document security testing results (SQL injection, XSS attempts)
            - Include performance stress testing observations
    - Grade & Prioritize - given the test case results from above
        - **Quality Guidelines for Grading:**
            - Provide unique, descriptive summaries for all defects
            - Justify severity levels with clear business impact analysis
            - Include complete reproduction steps and environment details
            - Attach screenshots or evidence for all reported issues
    - Iterate & Automate - allow reuse of these test cases, follow what's written in kintsugi.md, and prioritize using this flow: Detect → Reproduce → Automate → Monitor
        - **Quality Guidelines for Automation:**
            - Ensure test cases are reproducible by QA team
            - Provide automation recommendations with tool suggestions
            - Include monitoring strategies for critical business flows
            - Document lessons learned for future iterations 
4. **Create separate, human-readable test case files** that QA can easily understand.  
5. **Log defects** in the Excel file provided (on the sheet named ('Bug List')).

---

## 🐛 Logging Bugs

All bugs must be recorded in the file:  
📄 **`Defect List_Lucks.xlsx`** (located in the same directory as this file)

You can use **ExcelJS** to automate writing defects to this file.

### Excel Columns

| Column | Description |
|--------|--------------|
| **BUG #** | Unique identifier for the bug |
| **Bug Title** | Short summary of the issue |
| **Description** | Steps to reproduce the issue |
| **Expected Result** | What should happen |
| **Actual Result** | What actually happens |
| **Severity** | Critical / Major / Minor |
| **Other Details** | Additional notes or info |
| **Workaround** | Temporary fix, if any |
| **Artifacts (Screenshot / Logs)** | Path to screenshot or log file | you can use formula =HYPERLINK() for filepaths if you can
---
## ✅ Success Criteria

### Minimum Requirements:
- [ ] All 8 KINTSUGI phases completed with documentation
- [ ] At least 3 critical business flows tested
- [ ] Minimum 5 test cases created for QA team
- [ ] All found defects logged in Excel with complete details
- [ ] Security testing performed (SQL injection, XSS)
- [ ] Performance observations documented

### Quality Standards:
- Test cases must be reproducible by QA team
- Defects must include clear reproduction steps
- Risk assessment completed with impact analysis
- Automation recommendations provided
---

## 💡 Tips

- Focus on **quality over quantity**.  
- Make sure your tests and bug reports are **clear, consistent, and reproducible**.  
- Remember, the goal isn’t just to find bugs — it’s to **showcase great testing practices** using modern tools.

---

## 🚀 Let’s Do This!

Explore. Test. Report.  
Together, let’s make this Testathon a **winning run!**
