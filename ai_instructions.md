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
3. **KINTSUGI** follow the testing strategy in kintsugi.md, with the ff. details:
    - Know Context: short Context Card (1 paragraph) + top-3 critical flows
    - Instrument & Observe: 
        - Use Playwright to navigate the page
        - Observe console in dev tool during actions
        - Observe endpoints in dev tool -> Networks tab if requests are appropriately sent with their required use case (e.g., edits should have PUT endpoint calls to a server)
        - Observe overall functionalities and flow-of-action if they match the displayed strings in the Web UI elements
    - Make test cases using Context card from Know Context and add focus on the Instrument & Observe items for the following Principles:
        - Negative & Noise
        - Targeted Exploration
        - Simulate Real Users
        - Utilize Chaos
    - Grade & Prioritize - given the test case results from above
    - Iterate & Automate - allow reuse of these test cases, follow what's written in kintsugi.md, and prioritize using this flow: Detect → Reproduce → Automate → Monitor 
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

## 💡 Tips

- Don’t overdo it — this event runs for **2 days**, so **manage your energy**.  
- Focus on **quality over quantity**.  
- Make sure your tests and bug reports are **clear, consistent, and reproducible**.  
- Remember, the goal isn’t just to find bugs — it’s to **showcase great testing practices** using modern tools.

---

## 🚀 Let’s Do This!

Explore. Test. Report.  
Together, let’s make this Testathon a **winning run!**
