# PhishIntel

An intelligent, end-to-end phishing email analysis pipeline that combines fine-tuned transformer models (BERT) with durable workflow orchestration (Temporal) and exploratory data notebooks.

## Project Structure

```text
phish_intel/
├── data/                   # Raw and processed email datasets (gitignored)
├── models/                 # Saved model weights and Hugging Face checkpoints (gitignored)
├── notebooks/              # Exploratory data analysis and model prototyping
├── src/
│   └── phish_intel/
│       ├── __init__.py
│       ├── config.py       # Configuration and environment management
│       ├── core/           # Core ML code shared by CLI and Workflows
│       ├── ml_training/    # Automated model training and evaluation scripts
│       └── temporal/       # Temporal workflows, activities, and worker daemon
└── tests/                  # Unit and integration tests

```

## Getting Started

### Prerequisites

* Python 3.14 or higher
* [uv](https://github.com/astral-sh/uv) package manager
* [Temporal CLI](https://docs.temporal.io/cli) (for running local workflows)

### Installation

1. Clone the repository and navigate into the project directory:
```bash
git clone <repository-url>
cd phish_intel

```


2. Install dependencies using `uv`:
```bash
uv sync

```


3. Set up your environment variables by copying the example configuration (or creating a `.env` file):
```bash
cp .env.example .env

```



---

## Usage

### 1. Model Training

Run the automated training script to fine-tune the BERT model on your email dataset:

```bash
uv run phish-train

```

### 2. Running the Temporal Worker

Start the Temporal worker to process incoming email analysis jobs:

```bash
uv run phish-worker

```

*(Note: Ensure your local Temporal server is running via `temporal server start-dev` before starting the worker).*

### 3. Exploratory Notebooks

Launch [marimo](https://marimo.io) to explore data and prototype modifications to the model architecture:

```bash
uv run marimo edit notebooks/

```

---

## Development

Run tests to ensure everything is functioning correctly:

```bash
uv run pytest

```
