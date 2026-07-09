# ❓ Open Questions for Product Search Engine

These are the clarifying questions identified to refine the business requirements for the Advanced Product Search Engine.

## 1. Smart Autocomplete (Live Suggestions)
* **Q1.1 (Scope of Suggestions):** Will the autocomplete dropdown only show keyword suggestions (e.g., search terms) or also direct product suggestions (e.g., product name, image, price)?
* **Q1.2 (Personalization):** Should the system prioritize the user's recent search history over global popular search terms?

## 2. Multilingual Search & Translation
* **Q2.1 (Ingestion Translation):** When a seller creates a product, should we use an automated translation API (like Google Translate or LLM) or a predefined static dictionary maintained by admins?
* **Q2.2 (Mixed Queries):** How should the system handle mixed-language queries (e.g., "coffee Thái")?

## 3. Spellcheck & Synonyms
* **Q3.1 (Spellcheck Behavior):** Should the search auto-correct typos immediately (e.g., searching "samsng" directly searches "samsung"), or display a "Did you mean: Samsung?" prompt?
* **Q3.2 (Synonyms Mapping):** Are synonyms bidirectional (e.g., "instant noodles" <-> "ramen") or unidirectional?

## 4. Relevance & Ranking
* **Q4.1 (Ad Bidding Boost):** How should sponsored/featured product scores be balanced with keyword relevance scores?

## 5. Continuous Self-Learning Loop
* **Q5.1 (Suggestion Threshold):** How many times must an empty query be searched before it is queued for admin review?
