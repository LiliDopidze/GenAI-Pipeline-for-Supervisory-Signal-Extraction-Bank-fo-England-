# GenAI-Pipeline-for-Supervisory-Signal-Extraction-Bank-fo-England
# Surfacing Early Warning Indicators from Quarterly Financial Disclosures
This project develops a regulator-ready pipeline leveraging Natural Language Processing (NLP) and Generative AI (GenAI) to address a critical supervisory challenge: identifying subtle risk signals within unstructured quarterly earnings call Q&A transcripts. Traditional methods overlook evasive communication and linguistic cues (tone, sentiment) that may precede quantitative risk deterioration. This solution transforms complex, qualitative language into traceable, structured, and actionable risk insights for financial regulators like the Prudential Regulation Authority (PRA).

 # Key Features

- Modular GenAI/NLP Pipeline – Combines BERTopic, FinBERT, LLaMA 3.1, and Retrieval-Augmented Generation (RAG) for comprehensive topic modeling, sentiment analysis, and explainable reasoning.
- PRA-Aligned Risk Detection – Custom glossary and regex-driven rules label transcript blocks by supervisory risk category (e.g., Credit Risk, Liquidity & Funding, Capital & Leverage).
- Granular Signal Extraction – Detects explicit and proximity-based cues while weighting speaker roles and numeric intensity for severity scoring.
- Hidden Signal Surfacing – Uses LLaMA 3.1 to re-score ambiguous sentiment, identifying implicit negatives, executive guardedness, and uncertainty.
- Interactive RAG Chatbot – Enables supervisors to query risk signals by category, quarter, or speaker with concise, citation-linked answers.
- Visualization Support – Outputs structured data for dashboards (e.g., Azure SQL) to visualize evolving risk trends and sentiment heatmaps.

 # System Architecture 
The pipeline is structured into seven modular stages, ensuring transparent data flow and auditability:

1. Data Extraction: JSONL	Ingest raw transcripts and serialize them into a structured NLP input format.
2. Preprocessing: Cleansing, Pandas, Regex	Cleansing, speaker attribution, and robust Q&A pairing using turn-type logic.
3. Topic Modeling: BERTopic (UMAP + HDBSCAN), BGE-M3	Uncovers latent domain-specific risk themes and aligns them with regulatory frameworks.
4. Sentiment Analysis:	FinBERT + LLaMA 3.1 Refinement	Scores finance-specific sentiment and flags stress/guardedness (hidden tones).
5. Summarization:	LLaMA 3.1 (8B Instruct)	Generates concise, structured summaries per topic and quarter.
6. RAG Layer:	Hybrid Retrieval (BM25 + BGE)	Ensures all outputs are grounded in evidence via citation-linked, highly relevant context.
7. Signal Output:	Google Sheets / Azure SQL	Export final metrics and signals for interactive dashboard visualization.

# Contributors

- Claire Pache – Team Coordination & Strategic Narrative
- Alvaro Fernandez – Software Development
- Lili Dopidze – Model Research & Benchmarking
- Javier Igea – Industry Research & Benchmarking
- Oleksii Prosiankin – User Interface & Visualization
