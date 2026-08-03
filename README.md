# AI Candidate Matching & Recommendation Workflow

An AI-executed recruiting workflow that processes job descriptions and candidate resumes through a multi-step LLM prompt chain, producing structured, recruiter-ready output for human validation and submission.

**[Live Demo →](https://ai-recruiting-workflow-y7krow7ybylznak6shcmxu.streamlit.app/)**

---

## What It Does

This system automates the middle segment of a recruiting pipeline:

**JD Understanding → Candidate Matching → Recommendation → Validation Preparation → Submission-Ready Output**

For each candidate, the workflow generates:
- **Recommendation** — Ready to Submit / Validate First / Do Not Submit
- **Strengths and risks** with specific evidence from the resume
- **Recruiter validation questions** calibrated to recommendation tier
- **Client-ready summary** for submission to the hiring manager

---

## Features

- Upload any JD and any number of resume PDFs
- AI evaluates each candidate independently against structured JD requirements
- Recommendation table for at-a-glance review
- Expandable detailed reports per candidate
- Editable validation questions and client summaries
- Manual trigger to generate output for Do Not Submit candidates when recruiter overrides
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

- **Weighted requirement categories** replace numeric scoring to reflect how real recruiting decisions are made
- **No preset acceptance quota** — AI evaluates each candidate independently
- **temperature=0** ensures consistent, reproducible outputs
- **Do Not Submit candidates** do not receive validation questions or client summary by default, keeping the workflow clean — with a manual override option
- **Client summary** is generated pre-validation as a draft; recruiter edits are supported before export

---

## Tech Stack

- Python
- [Anthropic Claude API](https://www.anthropic.com/) — `claude-sonnet-4-6`
- Streamlit
- pypdf
- ReportLab
- python-docx
