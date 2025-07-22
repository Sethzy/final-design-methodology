---

### **Part 1: Strategic Brief**

## _(Phase 1 Final)_

**Elevator Pitch**
ThesisExplorer is a research platform that automates a rigorous, 11-step equity analysis workflow, turning any AI-growth stock ticker into a comprehensive investment thesis.

**Problem Statement**
Retail investors lack a systematic, repeatable framework for analyzing high-growth AI stocks, leading to inconsistent research, missed risks, and decisions based on hype rather than fundamentals.

**Target Audience**
Self-directed retail investors in the US and Singapore focused on identifying and validating high-growth AI equity opportunities.

**USP (Unique Selling Proposition)**
The core moat is the **codified, opinionated 11-step analysis workflow.** While competitors offer raw data or generic AI summaries, we provide a structured, repeatable analytical process designed specifically for the complexities of AI stocks. The value is in the *methodology*, not just the underlying API.

**Monetization Strategy**
Pay-per-report. Each generated thesis, which runs the full 11-step workflow, is a single transaction.

---

### **Part 2: MVP Scope & Roadmap**

## _(Phase 1 Final - v2)_

**In Scope for MVP: The "Generate Thesis" Core Feature**

The MVP is a single-page web app that executes the 11-step workflow for a user-provided ticker and renders a detailed, scrollable report.

- **UI - Input:** A single text field for the user to enter a company ticker symbol.
- **Backend - The Workflow Engine:**
  - Takes the ticker and orchestrates the 11-step analysis process.
  - For each step, it autonomously fetches the required data (e.g., SEC filings for 10-K, financial data APIs, targeted web searches for news/competitors) and feeds it to a deep research API (Perplexity/OpenAI) with specific prompts designed to produce the analysis required for that step.
- **UI - Output Report:** A single, scrollable page presenting the complete thesis, with clear sections matching the workflow:
  1.  **Phase 1: Macro & Competitive Landscape** (Industry Analysis, Thematic Alignment, Porter's Five Forces, Strategic Map).
  2.  **Phase 2: Company-Specific Deep Dive** (Moat Analysis, Advanced Financials with "Rule of 40", Management Scrutiny).
  3.  **Phase 3: Triangulation & AI Impact** (External Research, Bull/Bear Cases, AI Offensive/Defensive Strategy).
  4.  **Phase 4: Valuation & Execution** (Valuation Model, Technical Entry Point, Portfolio Management Plan).
  - Includes data visualizations where specified (e.g., strategic group map, financial ratio tables).

**Future Roadmap (Out of Scope for MVP)**

- **Future (V2.0):**
  - **Workflow Customization:** Allow advanced users to tweak, re-order, or add new steps to the analysis framework.
  - **Browser Automation (RPA) for Custom Data Sources:** A desktop agent or browser extension that lets users integrate paywalled content (e.g., newsletters, private research) by automating browser actions to log in, scrape, and ingest specified data into the workflow.

---

### **Part 3: Detailed Feature Specifications**

### Feature: Generate Report - Section 1: Macro & Competitive Landscape (Revised)

- **User Story:** "As a retail investor, I want to automatically analyze a company's industry attractiveness and competitive positioning, so that I can quickly decide if the company operates in a favorable environment before I spend time on a deep dive."
- **Business Goal:** This section delivers the initial "wow" moment by automating time-consuming top-down analysis. It validates the platform's power, justifying the per-report cost early in the user experience.
- **MVP Scope (The "How"):**
  - **Input:** User provides a valid company ticker (e.g., `NVDA`).
  - **Process:** The backend workflow engine initiates **API Call #1 (Deep Research): "External View"**. It uses the ticker to identify the company's industry and then feeds targeted prompts and data (from web searches, financial APIs) to the deep research API to generate:
    1.  **Industry Analysis:** A summary of the industry's growth prospects and structural attractiveness.
    2.  **Thematic Alignment:** Confirmation of which secular growth trends the company benefits from (e.g., AI, Cloud).
    3.  **Strategic Group Map:** A text-based description identifying the key strategic axes and where the company and its competitors fall.
    4.  **Porter's Five Forces:** A systematic, point-by-point analysis of the five forces, explaining the intensity of each for the specific company and industry.
  - **Output:** The rendered HTML report displays these four sub-sections in a clean, easy-to-read format.
- **UX/UI Considerations (Simplified):**
  - The report generation is an asynchronous process. Upon ticker submission, the UI will display a **single, simple loading indicator** (e.g., "Generating your report, please wait...") until the entire report is fetched and rendered.
  - The Strategic Group Map will be presented as **text or a very basic layout**. A complex, dynamic chart is out of scope for the MVP.
  - Each of the Porter's Five Forces will be a distinct **sub-header** for easy scanning.

### Feature: Generate Report - Section 2: The Deep Dive (Company-Specific Analysis)

- **User Story:** "As an investor, after confirming the industry is attractive, I want to perform a deep dive on the company's specific business quality, financial health, and management team, so I can build conviction that this is a superior horse in the race."
- **Business Goal:** This section provides the core fundamental analysis that separates a great company from a mediocre one. This is where the platform's depth and analytical rigor truly shine.
- **MVP Scope (The "How"):**
  - **Process:** This section is generated by **API Call #2 (Deep Research): The "Internal View"**.
  - The orchestrator triggers this call with the company ticker. It may also pre-fetch structured financial data (e.g., from a cheaper provider like IEX Cloud or EODhistoricaldata) and include it in the prompt for more accurate synthesis.
  - The API is prompted to generate analysis for:
    1.  **The Anatomy of a Moat:** A text-based table identifying the moat source (e.g., Network Effects), providing evidence, and rating its strength.
    2.  **Advanced Financial Forensics:** Analysis of key growth metrics (CAN SLIM), trends in revenue, ROE, FCF, and a table of key ratios (DSO, Quick Ratio, etc.).
    3.  **Management & Governance:** A summary of findings from proxy statements (compensation, board structure) and earnings call transcripts.
- **UX/UI Considerations (Simplified):**
  - Data will be presented as clean, formatted text and simple tables (e.g., using markdown).
  - Key metrics and red flags identified by the AI will be **bolded** for emphasis.

### Feature: Generate Report - Section 3: AI Impact Analysis

- **User Story:** "As an investor specializing in AI, I need a dedicated analysis of how AI specifically acts as a tailwind or a threat to this company, so I can validate if it truly fits my investment thesis."
- **Business Goal:** This is the killer feature for the target niche. It delivers the highly specific "AI-focused" analysis that generic platforms cannot, directly justifying the product's existence.
- **MVP Scope (The "How"):**
  - **Process:** This section is generated by **API Call #3 (Deep Research): "AI Impact View"**.
  - The orchestrator triggers this call with the company ticker.
  - The prompt is laser-focused on executing "Step 8: AI Impact Analysis" methodology, including:
    1.  **Offensive Strategy:** AI in products, AI in operations, Data as a moat.
    2.  **Defensive Strategy:** Risk of disruption, the "AI-Washing" test, competitive AI landscape.
- **UX/UI Considerations (Simplified):**
  - Clear sub-headers for "Offensive AI Strategy" and "Defensive AI Strategy".
  - Key conclusions (e.g., `Strong data moat identified` or `High risk of 'AI-Washing' detected`) will be **bolded**.

### Feature: Generate Report - Section 4: Synthesis & Action Plan

- **User Story:** "As an investor, once I have all the external, internal, and AI-specific facts, I want a concise final synthesis and an actionable plan so I can make a confident investment decision."
- **Business Goal:** This final section converts deep analysis into a clear decision, completing the user's journey and delivering the final "so what?" of the report.
- **MVP Scope (The "How"):**
  - **Process:** This section is generated by **API Call #4 (Reasoning Model)**.
  - The orchestrator takes the structured text outputs from the three completed deep research calls.
  - It sends this context to a standard, cost-effective reasoning model (e.g., GPT-4-Turbo, Claude 3 Sonnet).
  - The prompt asks the model to act as an analyst and, based _only_ on the provided context, generate:
    1.  **Valuation:** A brief analysis suggesting an appropriate valuation and what it implies.
    2.  **Triangulation & Decision:** A summary of the core bull vs. bear case and a final "checkpoint" decision.
    3.  **Execution Plan:** High-level suggestions for entry points and a long-term monitoring strategy.
- **UX/UI Considerations (Simplified):**
  - The valuation section will clearly state the method used (e.g., "Relative Valuation," "DCF Analysis") and the conclusion.
  - The entire section will be concise and formatted for quick, actionable reading.

---

### **Part 3.5: UI/UX Screen Flow**

To deliver the features outlined in the MVP and future roadmap, the application will require the following screens.

#### MVP Screens (V1.0)

1.  **Screen 1: Dashboard**

    - **Purpose:** The main entry point of the application. This is where users will initiate new reports and view their history.
    - **Key Components:**
      - A prominent header with the application name.
      - A single input field for entering a stock ticker, with a "Generate Thesis" button.
      - A table or list displaying previously generated reports (`id`, `ticker`, `created_at`, `status`).
      - Clicking a report in the list will navigate the user to the "Report View" screen.
      - The list will show real-time status updates for pending reports (e.g., "pending", "generating...").

2.  **Screen 2: Report View**
    - **Purpose:** To display the generated investment thesis in a clean, readable format. This screen is also responsible for showing the loading state of a new report.
    - **URL:** `/report/{report_id}`
    - **Key Components:**
      - **Loading State:** When a report status is "pending", this screen will display a simple loading indicator. It will periodically check for updates.
      - **Completed State:** Once the status is "completed", the screen will render the full report from the `report_data` JSON field.
      - The report will be formatted with clear headings and subheadings corresponding to the 11-step workflow.
      - Key data points and tables will be styled for readability.

#### Future Roadmap Screens (V2.0)

3. a Yes, but we willw ork on the UI in a structured section format later but it is out of scope.
   3 b We will do a separate chat window for follo-wup questions later but it is out of scope.

3)  **Screen 3: Workflow Editor**

    - **Purpose:** To allow advanced users to customize the core 11-step analysis framework.
    - **Key Components:**
      - A view that lists all steps of the analysis workflow.
      - Drag-and-drop functionality to re-order the steps.
      - An "edit" button for each step, which opens a modal or a sub-page to edit the underlying prompts and parameters for that step's API call.
      - Functionality to add or delete steps from the workflow.
      - A "Save" button to commit changes to the user's custom workflow.

4)  **Screen 4: Custom Data Sources Management**
    - **Purpose:** To manage the integration of paywalled or private content via the Browser Automation (RPA) feature.
    - **Key Components:**
      - A list of currently configured custom data sources.
      - Instructions and a download link for the required browser extension or desktop agent.
      - An "Add New Source" form to configure new data sources (e.g., giving it a name, specifying a URL, and defining what data to look for).
      - Status indicators to show if the connection to a data source is active/working.

---

### **Part 4: Technical Plan**

## _(Phase 3 - Recommendations for a Lean MVP)_

### System Design & Architecture

The goal is to have as few moving parts as possible. The recommended approach is a simple **Serverless Architecture using Supabase**.

- **Frontend:** A minimal Single-Page Application (SPA) built with React/Vite. It will manage state with standard React hooks.
- **Backend:** Two **Supabase Edge Functions**.
  1.  `generate-report`: This function is our main **Orchestrator**. It receives the ticker, creates a `reports` record in the database with a "pending" status, and then begins the 4-call API process. Once complete, it updates the database record with the final report data and a "completed" status.
  2.  `get-report-status`: A simple function that takes a `report_id` and returns the current status and data from the `reports` table. The frontend will poll this endpoint.
- **API Communication:** The frontend will communicate with the Edge Functions using `axios`.

### Database Schema (Supabase)

To support saving and retrieving reports, the project will include a simple Supabase database with one primary table.

- **Table: `reports`**
  - `id` (uuid, primary key) - The unique identifier for the report.
  - `ticker` (text) - The stock ticker for the report.
  - `status` (text) - The current state of the report generation ('pending', 'completed', 'failed').
  - `report_data` (jsonb) - The final JSON output containing the full, structured investment thesis.
  - `created_at` (timestamp) - When the report generation was initiated.

### Implementation Stack Recommendations

- **Frontend Framework:** React with Vite + TypeScript.
- **UI Components:** `shadcn/ui` + Tailwind CSS.
- **Backend:** Supabase Edge Functions.
- **Database:** Supabase Postgres.
- **API Communication:** `axios`.
- **Deployment:** The entire stack can be managed and deployed via Supabase's dashboard and CLI.
