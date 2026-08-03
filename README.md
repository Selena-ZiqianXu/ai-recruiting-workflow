# AI Candidate Matching & Recommendation Workflow

An AI-executed recruiting workflow that processes job descriptions and candidate resumes through a multi-step LLM prompt chain, producing structured output for human review and hiring decisions.

**[Live Demo →](https://ai-recruiting-workflow-y7krow7ybylznak6shcmxu.streamlit.app/)**

---

## What It Does

This system automates the middle segment of a recruiting pipeline:

**JD Understanding → Candidate Matching → Recommendation → Validation Preparation → Hiring-Ready Output**

For each candidate, the workflow generates:
- **Recommendation** — Move Forward / Validate First / Pass
- **Strengths and risks** with specific evidence from the resume
- **Validation questions** calibrated to recommendation tier
- **Candidate summary** for the hiring manager

---

## Features

- Upload any JD and any number of resume PDFs
- AI evaluates each candidate independently against structured JD requirements
- Recommendation table for at-a-glance review
- Expandable detailed reports per candidate
- Editable validation questions and candidate summaries
- Manual trigger to generate output for Pass candidates when reviewer overrides
- Export results as PDF or Word (.docx)

---

## How to Use

1. Open the [Live Demo](https://ai-recruiting-workflow-y7krow7ybylznak6shcmxu.streamlit.app/)
2. Enter your [Anthropic API Key](https://console.anthropic.com/) in the sidebar
3. Upload the JD PDF
4. Upload one or more resume PDFs
5. Click **Run Evaluation**
6. Review results, edit outputs if needed, and export

---

## Design Decisions

- **Weighted requirement categories** replace numeric scoring to reflect how real hiring decisions are made
- **No preset acceptance quota** — AI evaluates each candidate independently
- **temperature=0** ensures consistent, reproducible outputs
- **Pass candidates** do not receive validation questions or candidate summary by default, keeping the workflow clean — with a manual override option
- **Candidate summary** is generated pre-validation as a draft; edits are supported before export

---

## Tech Stack

- Python
- [Anthropic Claude API](https://www.anthropic.com/) — `claude-sonnet-4-6`
- Streamlit
- pypdf
- ReportLab
- python-docx
