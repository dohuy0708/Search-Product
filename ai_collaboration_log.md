# 🤖 AI Collaboration & Prompt Log

This document records the prompt engineering and iteration process used to build and refine the Amaze Product Search project.

## 1. Initial Draft Generation
* **Prompt:** "Tôi muốn viết BRD cho yêu cầu Product Search Engine, dự án hoạt động theo mô hình Agile."
* **AI Output:** Generated the initial structured BRD in [product_search_requirements.md](product_search_requirements.md) containing Goals, Personas, Functional Specs, and NFRs.

## 2. Interactive Presentation Setup & Git Prep
* **Prompt:** "search_business_presentation.html này tôi muốn đẩy lên github và cho sếp bấm vô xem thì làm sao, có nên deploy lên github.io hay làm gì không?"
* **AI Output:** Suggested using GitHub Pages or GitLab Pages, created a customized `.gitlab-ci.yml` file, and set up the repository for automated deployment.

## 3. Localization and Client Alignment
* **Prompt:** "search_business_presentation.html đang dùng text bằng tiếng việt, nhưng mà khách hàng tôi là người nước ngoài nên hãy dùng english, và sử dụng cả từ vựng thân thuộc gần gũi dễ hiểu."
* **AI Output:** Refactored the entire presentation HTML file, translating zones, node labels, edge descriptions, and interactive details into user-friendly English (e.g., changing "Bộ làm giàu dữ liệu AI" -> "AI Data Enricher", "Giao diện người mua" -> "Buyer App / Web").

## 4. Conflict Resolution & Branch Setup
* **Prompt:** [User encountered Git conflicts during rebase]
* **AI Output:** Ran local resolution commands on the host (`git checkout --theirs README.md`, `git rebase --continue`) and successfully pushed the codebase to GitLab.
