# 🛒 Advanced Product Search Engine — Project Overview

This document summarizes the comprehensive workflow when implementing the **Smart Product Search** feature for a multi-national e-commerce platform. It aims to clarify business requirements quickly and foster efficient collaboration under the **Agile** development model.

---

## 🎯 Project Outline & Workflow

To realize this feature, the end-to-end process is organized into **4 core steps**. You can quickly access each corresponding attached document:

### 1️⃣ Analysis & Clarifying
* **Process:** Research the client's initial requirements, analyze blind spots, and identify edge cases. From there, establish a detailed list of clarifying questions to align on the business logic.
* **Deliverable:** 📝 **[Open Questions & Clarifications](open_questions.md)** *(A list of open questions to send to the client for requirements alignment).*

### 2️⃣ Feature Decomposition & Visual Client Alignment
* **Process:** Map the system architecture and data flows into highly interactive visual diagrams (mockups/dashboards) so that the client and You can easily visualize the solution without reading dry technical specifications.
* **Visual Presentations:** 
  * 🌐 **[View Online (GitHub Pages)](https://dohuy0708.github.io/Search-Product/)** *(View the interactive presentation directly on your browser).*
  * 📈 **[Local File (Download & Run)](search_business_presentation.html)** *(Download and double-click to run locally).*

### 3️⃣ PRD Specification & MVP Planning
* **Process:** Draft a detailed Business Requirements Document (BRD/PRD) structured as **User Stories** with Gherkin-formatted **Acceptance Criteria (Given-When-Then)**, while planning release phases (MVP vs. Future Phases) for the Agile project.
* **Detailed Specifications:** 
  * 📄 **[Official Document (Word)](BRD_Product_Search_Engine.docx)** *(The official product specification document).*
  * 🔍 **[Quick View (Markdown)](product_search_requirements.md)** *(View directly on Git repository).*

---

## 🤖 AI Copilot Integration & Collaboration

This project utilizes AI as a collaborative copilot to accelerate requirements analysis, architecture visualization, and documentation. The AI integration was structured around three key initiatives:

### 1️⃣ Building the Interactive Presentations
* **Skill Utilized:** `effective-html` (`npx skills add plannotator/effective-html`)
* **Workflow:**
  1. **Input Requirements:** Fed the raw product specifications into the AI.
  2. **Actor Analysis:** Analyzed all key actors and system stakeholders interacting with the search engine.
  3. **Verification:** Verified the relationships and connection paths between these actors.
  4. **Code Generation:** Applied the HTML skill to generate interactive, self-contained presentation pages.
* **Output:** [search_business_presentation.html](search_business_presentation.html) *(interactive dashboard).*

### 2️⃣ Requirements Review & Gap Analysis
* **Skill Utilized:** `grill-me` (`npx skills@latest add mattpocock/skills --skill grill-me`)
* **Workflow:**
  1. **Input Specifications:** Fed the initial functional specs into the AI.
  2. **Role-play Simulation:** Instructed the AI to act as a senior Business Analyst (BA) to audit the document, pinpointing ambiguities, omissions, and hidden system blind spots.
  3. **Question Formulation:** Generated critical clarifying questions to align expectations before finalizing the designs.
* **Output:** [open_questions.md](open_questions.md) *(a prioritized list of open questions for client alignment).*

### 3️⃣ Drafting the Business Requirements Document (BRD)
* **AI Tool:** Leveraged Claude (utilizing its code capabilities to output well-formatted and structured documents).
* **Workflow:**
  1. **Draft Generation:** Fed the requirements into the AI to generate the initial structural draft of the BRD.
  2. **Peer Review:** Reviewed the generated stories, identifying formatting and logic fixes.
  3. **Enhancement Loop:** Prompted the AI with consolidated feedback to enhance the Gherkin Acceptance Criteria, followed by a final validation review.
* **Outputs:** 
  * [Official Document (Word)](BRD_Product_Search_Engine.docx) *(The official product specification document).*
  * [Quick View (Markdown)](product_search_requirements.md) *(the structured, Agile-ready BRD).*

---

🤖 **[AI Collaboration & Prompt Log](ai_collaboration_log.md)** *(Click to view the detailed prompt history and interaction logs).*
