# ❓ Open Questions for Product Search Engine (Agile Alignment)

Below is the list of key open questions to discuss and align on the requirements (Requirements Sign-off) with clients and stakeholders:

---

## 1. 🔍 Search History & Autocomplete
* **Q1.1 (Search History Priority):** Should the system prioritize displaying the user's recent search history (Search History) at the top of the autocomplete suggestions dropdown before showing global popular search terms?
* **Q1.2 (API Optimization & Debounce):** What is the minimum number of characters required to trigger the Autocomplete API call, and what is the finalized debounce delay time when the user pauses typing (note: currently proposing 1-2 seconds)?

---

## 2. ⚡ Load Capacity & Scalability
* **Q2.1 (Concurrent User Benchmark):** For a multi-national scale system, is the benchmark of 500 concurrent users (CCU) sufficient, or does it need to be scaled up to meet actual peak traffic?

---

## 3. 🌐 Translation Strategy
* **Q3.1 (Translation Timing):** To avoid redundancy and system latency, does the client prefer translating at product ingestion time (Ingestion-time translation - prioritizes search speed) or translating at search query time (Query-time translation - prioritizes storage size)?

---

## 📊 4. Relevance & Ranking Weights
* **Q4.1 (Ranking Formula & Weights):** What is the preliminary mathematical formula and the specific weight percentages among the factors (Title matches, Sponsored ads, Stock availability...) to configure the search engine ranking?

---

## 🤖 5. AI Self-Learning Rules
* **Q5.1 (Strange Keyword Detection):** What quantitative rules (e.g., search frequency thresholds) does the "strange keyword detection" mechanism rely on, and how often should the system scan this data?
