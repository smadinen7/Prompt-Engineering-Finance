# Phase 2: Prompt Engineering Mastery

## Introduction
In this phase, I designed a set of prompts to evaluate large language models (LLMs) in the Finance domain. The two tasks I selected are Information Synthesis and Question-Answering, which reflect key responsibilities of financial analysts. For each task, I developed three types of prompts — CLEAR, Few-shot, and Chain-of-Thought — to test different prompting strategies. Each prompt is accompanied by documentation that explains its design rationale, expected output characteristics, and potential failure modes with suggested mitigations. Together, these prompts form the foundation for Phase 3, where I will systematically evaluate model performance across multiple LLMs.

---

## Task 1: Information Synthesis

### Input 
Orion Tech reported revenue growth of 7% year-over-year, reaching $12.8 billion, supported by strong demand in cloud infrastructure and digital payments. Operating income increased 12% to $2.1 billion, with operating margin improving to 16.4% from 15.2% last year. However, international revenues declined 5% due to foreign exchange headwinds, and inventory levels climbed 9% compared to the prior quarter. The company also repurchased $500 million in shares during the quarter. Management projected revenue growth of 5–6% with stable margins for the next quarter.

Nova Retail posted revenues of $4.2 billion, flat compared to last year, while net income dropped 20% to $480 million due to higher interest expenses and a $75 million litigation settlement. Analysts noted that slowing consumer demand in North America and rising wage costs in logistics are ongoing challenges. The company announced plans to cut 1,500 jobs as part of a restructuring initiative expected to save $200 million annually starting in 2025.

Lyra Commerce delivered quarterly revenue of $6.7 billion, up 10% year-over-year and $300 million ahead of consensus estimates. Growth was driven by strong e-commerce sales, which rose 18%, and digital advertising, which increased 15%. Gross margin improved slightly to 22%, while operating expenses rose 11% due to higher R&D spending on AI-driven personalization tools. Management raised full-year guidance, forecasting revenue growth of 9–11% and margin expansion of 50 basis points. However, inflationary pressures and elevated logistics costs remain key risks for the next two quarters.

Across the industry, rising interest rates continue to pressure borrowing costs, particularly for firms with heavy debt exposure. Global shipping disruptions linked to ongoing labor disputes have extended delivery times by an average of 6–8 days, which could affect profitability in the upcoming quarter. At the same time, consumer spending has shown early signs of recovery in Asia, partially offsetting weakness in European markets.

---

### CLEAR Prompt for Task 1 (Information Synthesis)
**Context:** You are acting as a financial analyst reviewing recent company performance and sector updates. You are given financial summaries from three companies (Orion Tech, Nova Retail, and Lyra Commerce) along with broader industry risks.
  
**Length:** Write a concise synthesis in **200–250 words**.
  
**Examples:** A good summary should highlight key revenue/margin trends, risks, and forward guidance across all three companies, and connect them to the industry-wide context. For example:
- Correctly mentioning revenue growth and margin expansion for Orion Tech while noting inventory buildup.
- Highlighting Nova Retail’s earnings decline, legal costs, and restructuring efforts.
- Emphasizing Lyra Commerce’s strong e-commerce and digital advertising performance alongside cost pressures.
- Linking these company-level developments to broader risks like interest rates, shipping delays, and consumer demand shifts.

**Audience:** The output should be written for finance professionals, such as portfolio managers or senior analysts, who expect precise, professional, and neutral language.
  
**Role:** Take the role of an equity research analyst preparing a client-facing note.

**Task Input**  
*paste from above*

**Prompt Documentation:**
- **Design Rationale:** CLEAR provides structure, ensuring precision and professional tone by defining role, audience, and word length. This reduces vague or casual outputs.
- **Expected Output Characteristics:** 200–250 word synthesis covering Orion, Nova, Lyra, and sector risks; balanced positives/negatives; neutral, professional financial language.
- **Potential Failure Modes & Mitigation:** Too short/long → enforce word limit; focus on one company → require all three + sector; casual tone → specify analyst role & professional audience.

---

### Few-shot Prompt for Task 1 (Information Synthesis)
**Instruction to Model:** You are an equity research analyst. Below are examples of financial synthesis notes written for portfolio managers. Each example highlights revenues, margins, risks, and forward guidance. Read the examples carefully, then write a synthesis for the provided financial reports.

**Example 1**  
**Companies:** Helios Energy, Terra Renewables, Lumina Power  
**Summary:**  
Helios Energy reported 6% year-over-year revenue growth to $8.1 billion, supported by expansion in solar projects, though profit margins narrowed due to rising input costs. Terra Renewables posted flat revenues of $3.5 billion, with earnings pressured by higher financing costs, prompting management to suspend share buybacks. Lumina Power exceeded expectations with 12% revenue growth and margin expansion to 18%, driven by strong demand in battery storage solutions. Across the sector, regulatory incentives supported growth, but commodity price volatility remains a significant risk for the next two quarters.

**Example 2**  
**Companies:** Axis Pharma, BioNova Labs, Zenith Health  
**Summary:**  
Axis Pharma delivered 9% revenue growth to $5.9 billion, boosted by new oncology treatments, though R&D expenses weighed on profitability. BioNova Labs experienced a 7% revenue decline amid generic competition, and management issued cautious guidance for the second half of the year. Zenith Health posted solid 10% revenue growth, with strong international sales offsetting slower U.S. demand. Industry-wide, pricing pressure and rising regulatory scrutiny continue to create headwinds, though long-term demand for specialty drugs remains robust.

**Task Input**  
*paste from above*

Using the style of the examples, write a **200–250 word** synthesis that highlights key financial performance, risks, and guidance across Orion Tech, Nova Retail, Lyra Commerce, and the broader industry. Ensure your response is accurate, complete, and written in professional financial language.

**Prompt Documentation:**
- **Design Rationale:** Few-shot guides the model with concrete examples, aligning tone and structure with professional equity notes.
- **Expected Output Characteristics:** 200–250 word synthesis mirroring examples; covers Orion, Nova, Lyra, and sector risks; balanced insights with correct terminology.
- **Potential Failure Modes & Mitigation:** Hallucination or style drift → strong reference examples; ignoring sector risks → explicitly included; tone mismatch → examples reinforce professional voice.

---

### Chain-of-Thought Prompt for Task 1 (Information Synthesis)
**Instruction to Model:** You are an equity research analyst. Carefully read the financial information below about Orion Tech, Nova Retail, Lyra Commerce, and the industry context. Follow the step-by-step process before writing your final synthesis.

**Step-by-Step Reasoning (Chain of Thought):**
1. **Extract Key Figures and Trends:**
   - For each company, list revenues, growth rates, margins, income changes, major risks, and guidance.
2. **Identify Positives and Negatives:**
   - Highlight strengths (e.g., revenue growth, margin improvements) and weaknesses (e.g., rising costs, restructuring, inflation).
3. **Compare and Contrast Across Companies:**
   - Note differences in performance (growth vs. decline) and industry exposure.
4. **Incorporate Sector-Wide Risks:**
   - Summarize broader trends like interest rates, shipping delays, and regional consumer demand.
5. **Write the Final Synthesis:**
   - Produce a **200–250 word** professional summary that integrates company and industry findings.
   - Maintain financial precision and neutral, analytical tone.

**Task Input**  
*paste from above*

Using the style of the examples, write a **200–250 word** synthesis that highlights key financial performance, risks, and guidance across Orion Tech, Nova Retail, Lyra Commerce, and the broader industry. Ensure your response is accurate, complete, and written in professional financial language.

**Prompt Documentation:**
- **Design Rationale:** CoT ensures systematic reasoning—extract, compare, integrate—reducing omissions and bias.
- **Expected Output Characteristics:** 200–250 word synthesis, clear stepwise logic, professional financial tone, covering all firms and sector context.
- **Potential Failure Modes & Mitigation:** Overly verbose reasoning → require polished final output; missing sector context → embed explicit step; tone drift → reinforce “professional audience” in prompt.

---

## Task 2 Input – Regulatory & Risk Report
The financial oversight board issued a sector review highlighting risks in consumer retail and technology firms.

**Altura Systems** disclosed in its latest filings that foreign exchange headwinds reduced international revenues by 5% in the past quarter. The firm also reported a 10% rise in unsold inventory, raising concerns about aggressive production schedules. Debt maturity schedules show $3.1 billion in refinancing due in 2025, making Altura particularly vulnerable to rising interest rates.

**Crescent Retail** is under review for compliance with new labor regulations after recent layoffs of over 2,200 employees. The firm also faces ongoing litigation related to consumer data breaches, with potential liabilities estimated at $180 million. Analysts note that high short-term debt exposure leaves the company sensitive to further rate hikes.

**Vega Commerce** is expanding aggressively into Southeast Asia, where regulatory approval for digital advertising remains uncertain. Operating expenses grew 13% due to compliance costs and new regional hires. While revenues are growing, higher leverage ratios (debt-to-equity 1.8x) increase financial risk if interest rates stay elevated.

The report concludes that **systemic risks**—interest rate pressure, regulatory uncertainty, and global supply chain disruptions—are likely to challenge profitability across the sector in the next two quarters.

---

### CLEAR Prompt for Task 2 (Question-Answering)
**Context:** You are a financial risk analyst reviewing a regulatory report on three companies — Altura Systems, Crescent Retail, and Vega Commerce — along with sector-wide risks.
  
**Length:** Provide answers of **3–5 sentences per question**.
  
**Examples:** A good answer will:
- Identify company-specific risks (e.g., Altura’s refinancing, Crescent’s litigation, Vega’s regulatory approvals).
- Compare firms fairly (e.g., Crescent struggling with compliance vs. Vega growing but leveraged).
- Explain systemic issues (interest rates, regulation, supply chains) clearly and concisely.
- Adapt explanation style when needed (professional for analysts, plain language for non-experts).

**Audience:** Your answers will be read by portfolio managers and regulators, who need precise but clear analysis.
  
**Role:** Act as a financial risk analyst preparing responses to common stakeholder questions.

You are a financial risk analyst. Based on the following regulatory and risk report, answer the three questions below. Provide answers of **3–5 sentences each**, written in a professional and precise tone.

**Questions:**
1. What are the most significant risks each company faces in the next two quarters?
2. How does Crescent Retail’s risk exposure compare to Vega Commerce’s?
3. Explain in simple terms how rising interest rates might affect these companies, especially for a non-expert audience.

**Input:**  
*paste from above*

**Prompt Documentation:**
- **Design Rationale:** CLEAR adds structure for precise, professional QA across companies and sector risks.
- **Expected Output Characteristics:** 3–5 sentence answers per question; professional tone; covers Altura, Crescent, Vega, plus systemic risks.
- **Potential Failure Modes & Mitigation:** Too brief/verbose → specify sentence range; missing companies → explicitly name them; casual tone → define role & audience.

---

### Few-shot Prompt for Task 2 (Question-Answering)
**Instruction to Model:**
You are a financial risk analyst. Below are examples of how regulatory and financial risk questions are answered. Review these examples, then answer the three questions for the companies in the provided input.

**Example 1**  
**Question:** What are the biggest risks facing Horizon Motors in the next year?  
**Answer:** Horizon Motors faces two major risks. First, supply chain bottlenecks in semiconductor sourcing are expected to delay production and increase costs by 8%. Second, rising raw material prices have pressured margins, leading management to guide for lower profitability in the next two quarters.

**Example 2**  
**Question:** How does Solaris Retail’s risk profile compare to Zenith Apparel’s?  
**Answer:** Solaris Retail’s main risks are related to weak consumer demand and high short-term debt, which increases vulnerability to rate hikes. In contrast, Zenith Apparel is more exposed to international tariffs and supply chain delays, though it has stronger liquidity. Overall, Solaris is more financially fragile, while Zenith faces more operational and geopolitical risks.

**Example 3**  
**Question:** Explain in simple terms how higher interest rates affect companies with large amounts of debt.  
**Answer:** When interest rates go up, companies with a lot of debt must pay more to borrow money or refinance existing loans. This increases their expenses and reduces profits, leaving less cash for growth or dividends. It’s like how a household budget feels tighter when mortgage or credit card payments rise.

**Task Input**  
*paste from above*

Using the style of the examples, answer the following questions in **3–5 sentences each**, with clear, professional language appropriate for portfolio managers and regulators:
1. What are the most significant risks each company faces in the next two quarters?
2. How does Crescent Retail’s risk exposure compare to Vega Commerce’s?
3. Explain in simple terms how rising interest rates might affect these companies, especially for a non-expert audience.

**Prompt Documentation:**
- **Design Rationale:** Few-shot aligns model with example QA style, ensuring concise and professional responses.
- **Expected Output Characteristics:** 3–5 sentence answers; clear comparisons; professional but accessible tone; covers all companies and systemic risks.
- **Potential Failure Modes & Mitigation:** Hallucination → constrain to input; ignoring systemic risks → explicitly require; tone drift → examples enforce style.

---

### Chain-of-Thought Prompt for Task 2 (Question-Answering)
**Instruction to Model:**
You are a financial risk analyst. Carefully read the following regulatory and risk report about Altura Systems, Crescent Retail, and Vega Commerce. Answer the questions step by step before writing your final polished answers.

**Step-by-Step Reasoning (Chain of Thought)**
1. **Extract Key Risks for Each Company:**
   - Altura → FX headwinds, rising inventory, $3.1B refinancing in 2025.
   - Crescent → labor regulation review, litigation ($180M liability), short-term debt.
   - Vega → regulatory uncertainty in Southeast Asia, compliance costs, high leverage (1.8x debt-to-equity).
2. **Identify Systemic Risks:**
   - Rising interest rates = higher borrowing costs.
   - Global supply chain disruptions.
3. **Compare Crescent vs. Vega:**
   - Crescent → compliance + legal exposure, weaker demand.
   - Vega → strong growth, but high debt + regulatory uncertainty.
4. **Explain Interest Rates for Non-Expert:**
   - Higher rates = more expensive borrowing.
   - Companies with high debt must spend more on interest → lower profits.
   - Simple analogy: like households paying more on mortgages/credit cards.
5. **Write Final Polished Answers:**
   - Use professional financial language, 3–5 sentences per question.

**Task Input**  
*paste from above*

First perform the step-by-step reasoning above, then write your final answers in a professional, concise style. Provide **3–5 sentences per question**, suitable for portfolio managers and regulators.

**Questions:**
1. What are the most significant risks each company faces in the next two quarters?
2. How does Crescent Retail’s risk exposure compare to Vega Commerce’s?
3. Explain in simple terms how rising interest rates might affect these companies, especially for a non-expert audience.

**Prompt Documentation:**
- **Design Rationale:** CoT enforces systematic reasoning, ensuring no omissions in risk analysis.
- **Expected Output Characteristics:** 3–5 sentence answers, structured around extracted risks, comparisons, and simple analogies for non-experts.
- **Potential Failure Modes & Mitigation:** Model may output raw reasoning → require polished final answers; too technical → include explicit plain-language step.

---

## Conclusion 
The prompts created in this phase highlight how different prompting approaches shape model behavior in financial tasks. The CLEAR method provides structure and ensures consistency, especially for maintaining professional tone and length. The Few-shot method uses examples to guide style and depth, which is useful for tasks like financial summaries and structured Q&A. The Chain-of-Thought method enforces step-by-step reasoning, which helps with completeness and logical flow, particularly in comparative or explanatory questions. These six prompts, supported by their documentation, create a solid basis for Phase 3, where I will apply them to three different LLMs and assess outputs using predefined metrics such as accuracy, completeness, and accessibility.
