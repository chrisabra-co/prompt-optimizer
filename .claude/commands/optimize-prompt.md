# Optimize Prompt Command

**Version:** 1.0
**Purpose:** Analyze and optimize prompts using the OTA (Optimize-Then-Answer) Framework

---

## Analyze the User's Prompt

**User Prompt:** {{args}}

---

## Phase 1: Domain Detection

Analyze the prompt to determine its primary domain:

- **Code**: Programming, APIs, debugging, implementation, testing
- **UX**: UI design, interfaces, user experience, accessibility, usability
- **Data**: Analytics, statistics, calculations, SQL, metrics
- **Writing**: Articles, documentation, content creation, emails
- **Research**: Studies, investigations, comparisons, analysis
- **Finance**: ROI, budgets, pricing, revenue, costs
- **Product**: Features, roadmaps, strategy, market planning
- **Misc**: General or unclear domain

Based on keywords and context in the prompt, determine the domain.

---

## Phase 2: Clarity Analysis

Calculate clarity score (0-100%) based on these factors:

| Factor | Weight | Assessment Criteria |
|--------|--------|-------------------|
| **Goal Clarity** | 30% | Is there a clear objective? (create, build, analyze, etc.) |
| **Context** | 25% | Are inputs, constraints, and background provided? |
| **Format** | 15% | Is the output format specified? |
| **Criteria** | 20% | Are success criteria or requirements stated? |
| **Technical** | 10% | Are technical details (tools, versions) included? |

Assess each factor and calculate the overall clarity score.

---

## Phase 3: Risk Detection

Check for potential risks:

- **Security**: Authentication, passwords, tokens, vulnerabilities
- **Privacy**: PII, emails, phone numbers, GDPR concerns
- **Policy**: Fake content, bypassing systems, illegal activities
- **Safety**: Harmful or dangerous content
- **Compliance**: Medical/legal/financial advice without expertise

---

## Phase 4: Generate Optimization

### 4.1 If Clarity Score < 60%

Generate 1-3 targeted questions based on what's missing:

**For Code Domain:**
- What programming language or framework are you using?
- What specific feature or component are you building?
- Do you need tests, validation, or security considerations?

**For UX Domain:**
- Who are the target users?
- What platform (web, mobile, desktop)?
- What are the key user goals?

**For Data Domain:**
- What's the data structure/format?
- What specific metrics or calculations?
- What's the data volume?

**For Writing Domain:**
- Who is the target audience?
- What length (word count, pages)?
- What tone (formal, casual, technical)?

**For Other Domains:**
- Can you provide more context about your goal?
- What is the timeline or urgency?
- What constraints or requirements exist?

### 4.2 Create Optimized Prompt

Structure the enhanced prompt with:

1. **Domain-Specific Requirements**

   **For Code:**
   - Include code summary and complexity notes
   - Add security considerations
   - Provide test plan and example I/O
   - Include error handling strategies

   **For UX:**
   - Evaluate against usability heuristics
   - Include accessibility checklist (WCAG 2.1 AA)
   - Consider mobile responsiveness
   - Address error and loading states

   **For Data:**
   - Describe dataset shape and structure
   - Show calculation steps explicitly
   - Validate data and identify edge cases
   - Make results reproducible

   **For Writing:**
   - Define audience clearly
   - Specify tone and style
   - Include structure outline
   - Provide strong opening and CTA

2. **Output Format Specifications**
   - Structured and scannable format
   - Include acceptance criteria
   - List any assumptions made
   - Provide examples where helpful

3. **Risk Mitigation**
   - Address identified security concerns
   - Include necessary disclaimers
   - Add validation requirements

---

## Output Format

Provide the analysis in this format:

```
📊 PROMPT OPTIMIZATION REPORT
================================

🎯 Domain: [detected domain]
📈 Clarity Score: [X]%
⚠️ Risk Flags: [list any risks or "None"]

[If clarity < 60%:]
❓ CLARIFICATION NEEDED
-----------------------
To provide the best response, please answer:
1. [Question 1]
2. [Question 2]
3. [Question 3 if needed]

[If clarity >= 60%:]
✅ OPTIMIZED PROMPT
-------------------
[Provide the enhanced prompt with all domain-specific requirements,
structured format, and risk mitigations included]

💡 ENHANCEMENT NOTES
--------------------
- Added: [list key additions]
- Clarified: [list clarifications]
- Structure: [note on organization]
```

---

## Execution Instructions

1. Analyze the user's prompt for domain, clarity, and risks
2. Calculate the clarity score based on the weighted factors
3. If clarity < 60%, generate targeted questions and ask for clarification
4. If clarity >= 60%, provide the optimized prompt with all enhancements
5. Always include domain-specific requirements and risk mitigations
6. Format the output to be clear and actionable

Remember: The goal is to transform vague requests into clear, comprehensive prompts that will generate better AI responses.