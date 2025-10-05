### Overview
CodeGenie provides line-by-line natural language explanations of Python code using lightweight templates, with side-by-side comparisons across three Sentence-Transformers variants to highlight phrasing differences per model choice.
A Gradio interface is included to paste code, pick models, and view a comparison DataFrame of explanations for each line, alongside 10 included beginner-friendly code snippets for quick demos.

###Why This Project?

Learning to code isn’t just about writing syntax — it’s about understanding what the code means.
This tool is perfect for:

Students trying to break down complex code

Beginners who want simple explanations line by line

Researchers curious about how different language models interpret programming logic

### Features
- Line-level explanations via templates keyed to common constructs such as def, if, elif, else, for, while, assignment, print, and return.
- Three embedded models are loaded for explanation variants: all-MiniLM-L12-v2, all-distilroberta-v1, and all-mpnet-base-v2.
- A comparison DataFrame aligns each code line with the corresponding explanation per selected model for easy review.
- Gradio UI with a textbox for Python code, a checkbox group to select models, and a DataFrame output for the side-by-side comparison.
- Ten sample “Master_codes” snippets are included for immediate testing and illustration within the interface.

### Requirements
- Python 3 kernel and environment with access to pip, as the notebook kernelspec targets Python 3.[2]
- Packages installed in-notebook: sentence-transformers, nltk, textstat, pandas, matplotlib, wordcloud, and gradio.[2]
- NLTK data is fetched at runtime, including punkt_tab and stopwords, to support text processing steps.[2]

### Installation
The notebooks can be run directly in Jupyter or Colab; the first cell installs dependencies via pip and downloads the required NLTK resources automatically.[2]
For a local environment outside the notebook workflow, install the same dependencies with pip and ensure Python 3 is available before running the code cells.[2]

```bash
# Example local setup equivalent to the notebook
pip install sentence-transformers nltk textstat pandas matplotlib wordcloud gradio
python -c "import nltk; nltk.download('punkt_tab'); nltk.download('stopwords')"
```

### Run (Notebook interface)
Open CodeGenieV2.ipynb, run the setup cells to install dependencies and define the CodeExplainer and Gradio interface, then launch the app with iface.launch(...) to open the interactive comparison tool.[2]
The interface accepts pasted Python code and model selections, returning a DataFrame that compares generated explanations across the chosen models.[2]

```python
# In CodeGenieV2.ipynb after defining iface
iface.launch(share=True)
```

### Run (Programmatic use)
A helper function get_code_comparison(code_text, model_names) returns a pandas DataFrame comparing the explanations for each code line across the specified models, preserving the Line Number and Code columns.[2]
The underlying CodeExplainer class computes embeddings via the selected Sentence-Transformers backends and applies templated rules to produce concise, line-level explanations per model.[2]

```python
# In CodeGenieV2.ipynb
df = get_code_comparison(
    code_text="""
def add(a, b):
    return a + b
print(add(2, 3))
""",
    model_names=["MiniLM", "DistilRoBERTa", "MPNet"]
)
df  # pandas DataFrame with columns: Line Number, Code, MiniLM, DistilRoBERTa, MPNet
```

### Project structure
| File | Purpose |
|---|---|
| CodeGenieV1.ipynb | Baseline exploration producing line-by-line explanation comparisons across models to validate templates and outputs |
| CodeGenieV2.ipynb | Adds Gradio UI, defines get_code_comparison, includes 10 sample snippets, and summarizes setup and next steps |

### How it works
CodeExplainer loads three pretrained SentenceTransformer models and encodes each line to maintain contextual processing, while explanation selection relies on deterministic templates keyed to code constructs and model index for variant phrasing.
Templates are provided for constructs including def, if, elif, else, for, while, assignment, print, return, and a default fallback, yielding short, consistent explanations per line.

### Examples
The notebook prints a summary of the included “Top 10 Example of Code Masters,” listing each demo snippet and its character length for quick inspection.
The interface exposes one of these snippets as an example input so the DataFrame output can be viewed immediately without custom code pasted by the user.

### Notes and next steps
The current implementation treats embeddings as a “mock usage” to preserve model involvement while selecting explanation variants via model index and templates for predictable, comparable outputs.
Potential extensions include adding more models, richer templates per construct, and options for custom user-supplied model outputs or ranking heuristics across explanatory variants.

