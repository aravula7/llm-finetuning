# LLM Fine-tuning for SQL Generation

Fine-tune Mistral 7B for text-to-SQL using LoRA.

## Objective
Compare Base Mistral vs Fine-tuned vs GPT-4o for SQL query generation.

## Dataset
- 2,000 SQL query pairs (text-to-SQL)
- Domain: E-commerce warehouse schema
- Generated using GPT-4 + Spider dataset

## Training
- Colab notebook (A100 GPU, ~90 min)
- QLoRA (4-bit quantization)
- Rank: 16, Alpha: 32, Epochs: 2

## Evaluation Metrics
- Accuracy (executable + correct results)
- Latency P95
- Cost per 1K queries
- Human quality rating (1-5)

## Setup
```bash
# Local (for data generation)
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt

copy .env.example .env
# Add OpenAI key for dataset generation

# Training (Colab only)
# Upload notebook, run on A100
```

## No Deployment
Training and evaluation only - results saved in results/