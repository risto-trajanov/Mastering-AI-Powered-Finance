# Mastering AI-Powered Finance: Companion

Companion material for the book *Mastering AI-Powered Finance*.

- **Website:** https://risto-trajanov.github.io/Mastering-AI-Powered-Finance/
  One hands-on AI tutorial page for each of Chapters 2 through 9. Chapters 1 and 10 have no tutorial.
- **Notebooks:** the `notebooks/` folder holds one Jupyter notebook per chapter, with saved outputs, plus the data files each one needs.

## Notebooks

| Chapter | Notebook |
| --- | --- |
| 2 | [The Importance of Data](notebooks/chapter-02-the-importance-of-data/chapter_notebook.ipynb) |
| 3 | [Machine Learning Techniques](notebooks/chapter-03-machine-learning-techniques/chapter_notebook.ipynb) |
| 4 | [Generative AI in Finance](notebooks/chapter-04-generative-ai-in-finance/chapter_notebook.ipynb) |
| 5 | [AI Agents](notebooks/chapter-05-ai-agents/chapter_notebook.ipynb) |
| 6 | [AI and Algorithmic Trading Strategies](notebooks/chapter-06-ai-and-algorithmic-trading-strategies/chapter_notebook.ipynb) |
| 7 | [Socio-Technical Transformation of Algo Trading](notebooks/chapter-07-socio-technical-transformation-of-algo-trading/chapter_notebook.ipynb) |
| 8 | [AI-Powered Equity Investing](notebooks/chapter-08-ai-powered-equity-investing/chapter_notebook.ipynb) |
| 9 | [AI in Portfolio Optimization](notebooks/chapter-09-ai-in-portfolio-optimization/chapter_notebook.ipynb) |

The trading tutorial runs across Chapters 6 and 7, and the equity tutorial across Chapters 8 and 9.

## Running the notebooks

Python 3.11 was used. From this folder:

```bash
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab notebooks
```

Run each notebook from top to bottom, with its own chapter folder as the working directory. Market-data examples use the bundled snapshots in each `data/` folder so results reproduce; set `REFRESH_MARKET_DATA=1` to download current data instead.

The examples that call a live language model are off by default. To run them, set `RUN_LIVE_API=1` and the provider key named in the notebook (`OPENAI_API_KEY` or `ANTHROPIC_API_KEY`). Those calls are billed by the provider.

The examples demonstrate methods. They are not investment advice, and synthetic data is labelled where it is used.

## Layout

- `docs/`: the built website, served by GitHub Pages.
- `notebooks/`: the chapter notebooks and their data.
- `requirements.txt`: the package versions the notebooks were run with.
