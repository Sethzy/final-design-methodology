You reformat to use XML tags:

Use XML tags can be a game-changer. They help Claude parse your prompts more accurately, leading to higher-quality outputs.

XML tip: Use tags like <instructions>, <example>, and <formatting> to clearly separate different parts of your prompt. This prevents Claude from mixing up instructions with examples or context.

Tagging best practices
Be consistent: Use the same tag names throughout your prompts, and refer to those tag names when talking about the content (e.g, Using the contract in <contract> tags...).
Nest tags: You should nest tags <outer><inner></inner></outer> for hierarchical content.
Power user tip: Combine XML tags with other techniques like multishot prompting (<examples>) or chain of thought (<thinking>, <answer>). This creates super-structured, high-performance prompts.

Example 1: Generating financial reports

Bad Input without XML tags:

You’re a financial analyst at AcmeCorp. Generate a Q2 financial report for our investors. Include sections on Revenue Growth, Profit Margins, and Cash Flow, like with this example from last year: {{Q1_REPORT}}. Use data points from this spreadsheet: {{SPREADSHEET_DATA}}. The report should be extremely concise, to the point, professional, and in list format. It should and highlight both strengths and areas for improvement.

Bad Output becasue no XML tags were used in the input:

Q2 Financial Report for AcmeCorp Investors

Dear Valued Investors,

I am pleased to present our Q2 financial report, showcasing AcmeCorp’s continued growth and resilience in the B2B SaaS market.

1. Revenue Growth:
   Our Q2 revenue reached $15.2M, a 22% YoY increase. This growth is primarily driven by a 30% expansion in our enterprise client base. However, our SMB segment saw a slight decline of 5%, which we aim to address through targeted marketing initiatives in Q3.

2. Profit Margins:
   Gross margin improved to 72% (up 3% from Q1) due to infrastructure optimizations. EBITDA margin, however, dipped to 18% (down 2%) as we invested heavily in R&D for our upcoming AI-driven features.

3. Cash Flow:
   Operating cash flow remains strong at $4.1M. Our cash reserves stand at $28M, providing a 15-month runway at current burn rate. We did see a 20% increase in customer acquisition costs, which we’re addressing through more efficient sales strategies.

In summary, AcmeCorp’s core financials remain robust. We’re balancing growth investments with prudent cash management. Our focus for Q3 will be revitalizing SMB growth and optimizing sales efficiency.

Thank you for your continued trust.

Sincerely,
CFO, AcmeCorp

Good input becasue XML tags were used:

You’re a financial analyst at AcmeCorp. Generate a Q2 financial report for our investors.

AcmeCorp is a B2B SaaS company. Our investors value transparency and actionable insights.

Use this data for your report:<data>{{SPREADSHEET_DATA}}</data>

<instructions>
1. Include sections: Revenue Growth, Profit Margins, Cash Flow.
2. Highlight strengths and areas for improvement.
</instructions>

Make your tone concise and professional. Follow this structure:
<formatting_example>{{Q1_REPORT}}</formatting_example>

Good output because XML tags were used:

Q2 Financial Report for AcmeCorp Investors</output>

Revenue Growth:

- Q2 revenue: $15.2M (22% YoY ↑)
- Enterprise clients: 30% ↑
- SMB segment: 5% ↓
  Action: Targeted Q3 marketing

Profit Margins:

- Gross margin: 72% (3% ↑ from Q1)
  Reason: Infrastructure optimizations
- EBITDA margin: 18% (2% ↓)
  Reason: R&D investment in AI features

Cash Flow:

- Operating cash flow: $4.1M (strong)
- Cash reserves: $28M (15-month runway)
- Customer acquisition cost: 20% ↑
  Action: Optimize sales strategies

Outlook:

- Core financials: Robust
- Q3 focus: Revitalize SMB, optimize sales

Management remains committed to balancing growth investments with financial discipline.

Example 2: legal contract analysis:

Without XML tags, Claude’s analysis is disorganized and misses key points. With tags, it provides a structured, thorough analysis that a legal team can act on.

Bad input prompt example without XML tags:

Analyze this software licensing agreement for potential risks and liabilities: {{CONTRACT}}. Focus on indemnification, limitation of liability, and IP ownership clauses. Also, note any unusual or concerning terms. Here’s our standard contract for reference: {{STANDARD_CONTRACT}}. Give a summary of findings and recommendations for our legal team.

Bad output because of no XML tags:

The provided software licensing agreement presents several concerning aspects. The indemnification clause is overly broad, potentially exposing us to significant liabilities. The limitation of liability section caps damages at a mere $500, which is inadequate for our enterprise-level usage. Regarding IP, the agreement grants the vendor joint ownership of any modifications or integrations we create.

In summary, this agreement is not in our best interest. It exposes us to undue risk, limits our recourse in case of failures, and compromises our intellectual property rights. I recommend renegotiating these terms or seeking alternative vendors.

Good input because of XML tags:

Analyze this software licensing agreement for legal risks and liabilities.

We’re a multinational enterprise considering this agreement for our core data infrastructure.

<agreement>
{{CONTRACT}}</agreement>

This is our standard contract for reference:
<standard_contract>{{STANDARD_CONTRACT}}</standard_contract>

<instructions>
1. Analyze these clauses:
- Indemnification
- Limitation of liability
- IP ownership

2. Note unusual or concerning terms.

3. Compare to our standard contract.

4. Summarize findings in <findings> tags.

5. List actionable recommendations in <recommendations> tags.</instructions>

Good output because of XML tags:

<findings>
1. Indemnification (Clause 8):
- Issue: Overly broad. We indemnify vendor against “any and all claims” arising from our use.
- Risk: Could hold us liable even for vendor’s negligence or product defects.
- Deviation: Our standard limits indemnity to claims arising from our violation of agreement.

2. Limitation of Liability (Clause 9):

- Issue: Caps all damages at $500, including direct damages.
- Risk: Grossly inadequate for enterprise use. A critical failure could cost millions.
- Deviation: Our standard allows for direct damages up to 12 months of fees paid.

3. IP Ownership (Clause 12):

- Issue: Grants vendor joint ownership of our modifications/integrations.
- Risk: Vendor could use or sell our proprietary algorithms or data insights.
- Deviation: Our standard retains full ownership of our work.

4. Unusual Terms:

- Clause 5.3: Vendor can use our usage data for “any purpose.”
- Clause 7.2: Vendor can terminate for “convenience” with only 7 days’ notice.
- Clause 11: No warranties of any kind, even for basic merchantability.
  </findings>

<recommendations>
1. Reject this agreement. Risks far outweigh benefits for an enterprise.
2. Counter-propose:
- Indemnification: Limit to claims arising from our violation of agreement.
- Liability: Cap at 12 months’ fees for direct damages; negotiate for indirect.
- IP: Full ownership of our modifications/integrations.
- Data Use: Restrict to service improvement only.
- Termination: Minimum 90 days’ notice; only for cause.
- Warranties: Demand basic merchantability and fitness for purpose.
3. If vendor refuses, explore alternative providers or in-house solutions.
4. Engage legal counsel for contract negotiation given high stakes.
</recommendations>
