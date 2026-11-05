A toolkit for evaluating and analyzing Retrieval-Augmented Generation (RAG) pipelines. RAGnalyze helps you measure how well your retriever finds the right context and how faithfully your generator uses it, then pinpoint where the pipeline fails.
Features
Test set support: questions with reference answers and source passages (simple, multi-document, and unanswerable questions)
Retrieval evaluation: Recall@k, Precision@k, MRR, nDCG
Generation evaluation: faithfulness, answer relevance, correctness vs. reference
Error analysis: categorize failures (wrong chunk, incomplete context, hallucination, wrongful refusal)
Ablation studies: compare chunk size/overlap, embedding models, hybrid search (BM25 + dense), and reranking
Reports: comparison tables and plots for quality / cost / latency trade-offs
Project Structure
RAGnalyze/
├── data/            # corpus and evaluation dataset
├── src/             # pipeline, metrics, and evaluation code
├── notebooks/       # analysis and visualization notebooks
├── results/         # metrics, tables, and plots
├── requirements.txt
└── README.md
Adjust this tree to match the actual layout of the repository.
Getting Started
Prerequisites
Python 3.9+
An LLM / embedding provider API key (if using hosted models)
Installation
git clone https://github.com/topxashishsinghhh-sketch/RAGnalyze.git
cd RAGnalyze
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate
pip install -r requirements.txt
Configuration
Create a .env file for your keys:
OPENAI_API_KEY=your_key_here
Usage
Place your documents in data/ and your evaluation questions in the test set file.
Run the evaluation:
python src/evaluate.py --config config.yaml
Open the notebooks in notebooks/ to explore metrics, plots, and error breakdowns.
Evaluation Metrics
Stage
Metrics
Retrieval
Recall@k, Precision@k, MRR, nDCG
Generation
Faithfulness, Answer relevance, Answer correctness
System
Latency, cost per query
Evaluation can use RAGAS, DeepEval, TruLens, or an LLM-as-judge with a scoring rubric.
Results
Add your comparison table here, for example:
Config
Recall@5
Faithfulness
Latency (s)
Baseline
-
-
-
+ Hybrid search
-
-
-
+ Reranker
-
-
-
Roadmap
[ ] Add more datasets
[ ] Support additional vector stores
[ ] Automated report generation
Contributing
Contributions are welcome. Fork the repo, create a feature branch, and open a pull request.
License
Add a license (e.g., MIT) and reference it here.
Author
topxashishsinghhh-sketch
