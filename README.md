# Labor Court Rulings Classification

A Jupyter notebook that uses the Anthropic API (Claude) to classify Italian labor court rulings (*sentenze*) into 5 outcome categories, and compares model results against human-labeled ground truth.

## Categories

1. **Decorrenza termini** — procedural category, takes priority
2. **Esito a favore del lavoratore** — ruling in favor of the employee
3. **Esito a favore del datore** — ruling in favor of the employer
4. **Ambiguo** — outcome unclear
5. **Non classificato** — too vague or unrelated to labor law

## What it does

- Loads a dataset of ruling abstracts with two human-labeled reference columns (`esito1`, `esito2`)
- Classifies each abstract using Claude via the Anthropic API
- Computes concordance between the LLM classification and both human labels
- Visualizes category distribution and inspects disagreement cases
- Exports classified results (`sentenze_classificate.csv`) and a run summary (`classificazione_summary.json`)

## Results

On a set of 159 rulings, the LLM classification showed 86.2% concordance with the first human labeler and 64.2% with the second, with 59.1% full three-way agreement.

## Setup

```bash
pip install anthropic pandas matplotlib
```

Set your API key as an environment variable rather than hardcoding it:

```bash
export ANTHROPIC_API_KEY="your_key_here"
```

## Note

Code comments and print statements inside the notebook are in **Italian**.
