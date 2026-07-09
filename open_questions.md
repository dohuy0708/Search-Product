# ❓ Open Questions for Product Search Engine (Agile Alignment)

Below is the list of open questions, summarized and categorized, to discuss and align on the requirements (Requirements Sign-off) with clients and stakeholders:

---

## 1. 🔍 Smart Autocomplete (Live Suggestions)
* **Q1.1 (Personal Search History):** Should the system prioritize displaying the user's recent search history at the top of the autocomplete suggestions dropdown before showing global popular search terms?
* **Q1.2 (Limits & Clearing History):** What is the maximum number of historical search terms to be saved? Is a feature to clear history needed (allowing clearing individual terms or clearing all history)?
* **Q1.3 (Activation Trigger):** How many minimum characters must the user type to trigger the Autocomplete API call (e.g., minimum of 2 or 3 characters)?
* **Q1.4 (Debounce Parameter):** What is the debounce time in milliseconds when the user pauses typing? *(Recommendation: 200ms - 300ms to optimize request volume and ensure actual response speed instead of 1-2 seconds).*

---

## 2. ⚡ Performance & Scalability
* **Q2.1 (CCU vs. RPS Metrics):** Is the figure "500 concurrent visits" in the document defined as the number of concurrent online users (CCU) or the number of requests the system must handle in 1 second (RPS)?
* **Q2.2 (Peak Load Projection):** How many times is the peak load during multi-national Flash Sale campaigns projected to increase compared to the 500 benchmark, so the team can prepare the appropriate infrastructure design?

---

## 3. 🌐 Multilingual & Translation
* **Q3.1 (Optimal Translation Strategy):** At what point should the system translate product titles/descriptions?
  * **Ingestion-time translation:** Translate and store when the seller uploads the product (Priority: extremely fast search speeds for buyers due to pre-indexed translations).
  * **Query-time translation:** Translate on-the-fly when the user types a search query (Priority: saves index storage space in the database).

---

## 4. 📊 Relevance & Ranking Rules
* **Q4.1 (Detailed Weights):** What are the exact weight percentages (%) between the ranking factors (Title match, Description match, Sponsored products, Stock availability)?
* **Q4.2 (Sponsored Product Placement):** Are sponsored/advertised products prioritized and fixed at the top of the results page (e.g., fixed top 3 positions) or are they just given a boost score in the general ranking algorithm?

---

## 5. 🤖 AI Self-Learning Feedback Loop
* **Q5.1 (Zero-Result Query Threshold):** What are the quantitative criteria for the system to identify a search term as a "strange/new keyword" for analysis? *(e.g., minimum search frequency of X times per week with zero results).*
* **Q5.2 (Cron Scan Frequency):** How often should the background worker/cron job run to scan and analyze new keywords? *(Hourly, daily, or batched at midnight when system load is low)?*

---

## ⚙️ 6. Admin Control Center & Access Control (Admin UI)
* **Q6.1 (Keyword Action Items):** What are the specific action items/features on the Admin UI screen for handling keyword suggestions? *(e.g., Approve, Reject, Edit, Merge synonyms).*
* **Q6.2 (Role-Based Permissions):** Does the approval workflow on the Admin UI require role-based access control? *(e.g., Operations staff can only Edit/Merge synonym groups, while Managers/Admins can click Approve to apply live changes).*
