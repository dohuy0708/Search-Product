# 🛒 Amaze Advanced Product Search Engine

A smart, high-speed, and multilingual product search engine designed for global B2B/B2C e-commerce platforms. This project translates complex business goals into agile technical blueprints with real-time analytics and continuous self-learning loops.

---

## 🔗 Live Presentations (Interactive Diagrams)
Once deployed via **GitLab Pages**, you can view the live interactive dashboards directly in your browser:

* 📈 **[Business Value Presentation (Click to View)](https://<your-gitlab-group-or-username>.gitlab.io/<your-repo-name>/index.html)**
  * *Shows how query routing, translation, and ad bidding directly impact conversion rates, premium UX, and business revenue.*
* 🛠️ **[System Architecture Map (Click to View)](https://<your-gitlab-group-or-username>.gitlab.io/<your-repo-name>/architecture.html)**
  * *Explores technical components, caching layers, and decoupled messaging pipelines (Kong Gateway, Redis, Elasticsearch, Kafka).*

*(Note: Please replace `<your-gitlab-group-or-username>` and `<your-repo-name>` with your actual GitLab project paths after deployment).*

---

## 📋 Project Deliverables

1. **Agile Business Requirements Document (BRD):**
   * Located at [product_search_requirements.md](product_search_requirements.md).
   * Maps business objectives into detailed Agile Epics, User Stories, and Gherkin Acceptance Criteria.
2. **Multi-language Search & Query Translation Pipeline:**
   * Features specialized English, Vietnamese, and Thai segmenters and dictionaries.
   * Auto-enrichment during ingestion and query expansion during search times.
3. **Smart Ranking Rules:**
   * Ranks items based on Text Relevance, Sponsored Keywords (Ad bidding), and Stock Availability.
4. **AI-Driven Continuous Learning Loop:**
   * Automatically captures zero-results queries and queues spelling and synonym corrections for operational review.

---

## 🛠️ Technology Stack
* **API Gateway:** Kong / Apache APISIX (Routing, security, and multi-tenancy)
* **Search Engine:** Elasticsearch (Fuzzy matches, multi-lingual tokenization)
* **Cache:** Redis (Autocomplete RAM cache < 5ms)
* **Message Queue:** Kafka / RabbitMQ (Decoupled logs and updates)
* **Database:** PostgreSQL / MySQL (Transactional source of truth)
