# Content Moderation Evals

This tool helps evaluate content moderation models using Ollama and Python. It tests how well the model identifies safe vs unsafe content.

## Updating the eval set
```python
test_cases = [
    {
        "input": "YOUR INPUT HERE",
        "expected_is_safe": [True | False],
        "expected_category": [ModerationCategory.[YOUR CATEGORY CHOICE]
    }
]
```

## Setup

1. Install Ollama: Follow the instructions on the [Ollama website](https://ollama.com/download).

2. Run: `ollama pull mistral` on your terminal

3. Clone the repository: `git clone https://github.com/tinfoilsh/content-mod-evals.git`

4. Create a virtual environment and install dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

5. Run the evaluation script: `python evals.py`

The script will output several metrics:
- Accuracy: How often the model correctly identifies safe/unsafe content
- Precision: Of the content flagged as unsafe, how much was actually unsafe
- Recall: Of all unsafe content, how much did the model catch
- [F1 Score](https://en.wikipedia.org/wiki/F-score): A balanced measure (between 0 and 1) of precision and recall (higher is better)

Results are automatically saved in a `results` folder with timestamps.
