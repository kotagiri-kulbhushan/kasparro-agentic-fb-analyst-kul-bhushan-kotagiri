Kasparro Agentic FB Analyst – Assignment Submission
By: Kul Bhushan Kotagiri

This repository contains my end-to-end solution for the Kasparro Applied AI Engineer Assignment.
I’ve built a clean, modular, and production-style multi-agent analysis pipeline that processes a synthetic Facebook Ads dataset and produces:

Data cleaning & preparation

Campaign-level insights

Hypothesis evaluation

Creative recommendations

A final structured performance report

The system follows a simple but powerful Planner → Evaluator → Generator pattern inspired by LLM-style reasoning workflows.

 1. Project Structure
kasparro-agentic-fb-analyst-kul-bhushan-kotagiri/

│

├── data/

│   └── synthetic_fb_ads_undergarments.csv

│

├── src/

│   ├── run.py

│   ├── orchestrator.py

│   └── agents/

│       ├── data_agent.py

│       ├── insight_agent.py

│       ├── evaluator_agent.py

│       ├── creative_agent.py

│       └── planner.py

│

├── reports/

│   ├── insights.json

│   ├── creatives.json

│   └── report.md

│

├── requirements.txt

├── .gitignore

└── README.md


Each part of the project is separated for readability, debugging, and easy iteration—similar to a real production pipeline.

 2. Agent Architecture (LLM-Inspired Workflow)

The system uses five lightweight agents, each responsible for only one part of the workflow.
This keeps the logic clean and makes the pipeline easy to audit or extend.

1. DataAgent

Loads, cleans, and prepares the input Facebook Ads dataset.

2. PlannerAgent

Acts as a coordinator:

Splits the dataset by campaign

Checks if a campaign has enough data to analyze

Decides which agents should run next

3. InsightAgent

Computes all key marketing KPIs:

CTR, CPC, CPM

CVR, ROAS

Clicks, reach, spend, impressions

4. EvaluatorAgent

Evaluates hypothesis-style checks, such as:

Is CTR dropping?

Is CPC unusually high?

Is ROAS below a healthy threshold?

The output is a clear “OK / Needs Attention” style evaluation.

5. CreativeAgent

If any metrics underperform, this agent generates simple rule-based suggestions for new creative ideas.

 3. Setup Instructions
Clone the repository
git clone https://github.com/kotagiri-kulbhushan/kasparro-agentic-fb-analyst-kul-bhushan-kotagiri.git
cd kasparro-agentic-fb-analyst-kul-bhushan-kotagiri

Create and activate a virtual environment (Windows)
python -m venv venv
venv\Scripts\activate

Install dependencies
pip install -r requirements.txt

 4. Run the Pipeline

To start the full multi-agent system:

python -m src.run


This will automatically:

Process all campaigns in the dataset

Generate insights per campaign

Evaluate hypotheses

Suggest creatives where needed

Save all outputs in the reports/ folder

 5. Outputs Generated
insights.json

Machine-readable KPI breakdown for each campaign.

creatives.json

Generated creative suggestions for underperforming campaigns.

report.md

A human-readable summary that includes:

Campaign name

Insights

Evaluations

Creative recommendations

 6. Evaluation Checklist

A file named EVAL_CHECKLIST.md is included for self-review.
It covers key criteria such as:

Modularity

Traceability

Code clarity

Output quality

Pipeline structure

 7. Release Tag

A GitHub release named v1.0 has been published as required.

 8. Author

Kul Bhushan Kotagiri
Applied AI Engineer Assignment – Kasparro.AI

- Ready for Evaluation

This repository includes everything needed for assessment:

 Fully functional agentic pipeline
 Clean and modular codebase
 insights.json
 creatives.json
 Final report.md
