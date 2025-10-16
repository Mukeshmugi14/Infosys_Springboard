##🚀 Code Generation Model Benchmark Toolkit

This project is your ultimate toolkit for evaluating and comparing small-to-medium Large Language Models (LLMs) on code generation tasks. Go beyond basic output checks—this notebook uses quantitative software metrics to provide a truly objective analysis of model performance.

🌟 Key Features

🧪 Head-to-Head Model Comparison: Benchmark four leading code-generation models—DeepSeek-Coder, Phi-2, Gemma, and Stable-Code—side by side.

💻 Interactive Gradio Dashboards: Two user-friendly Gradio interfaces allow real-time testing and model comparison.

📊 Advanced Code Metrics: Measure Cyclomatic Complexity, Maintainability Index, and Lines of Code using the radon library.

⏱️ Performance Analysis: Track generation speed and compare inference times across models.

📈 Automated Testing & Visualization: Run a suite of 16 standard coding prompts and generate insightful visualizations for easy analysis.

📝 Notebook Workflow

The notebook guides you step-by-step from setup to full evaluation:

Step	Section	Description
1	Setup & Authentication	Install libraries (transformers, torch, radon, etc.) and authenticate with Hugging Face to download model weights.
2	Core Engine	Functions for cleaning outputs, validating Python syntax (ast), calculating code metrics (radon), and generating code.
3	Model Pre-loading	Load all four models and their tokenizers into GPU memory using memory-efficient bfloat16 precision.
4	Interactive Gradio Dashboards	Deploy two dashboards: benchmark a single prompt across all models or compare custom model selections.
5	Automated Benchmark	Execute 16 coding prompts across all models to gather robust evaluation data.
6	Visualization	Aggregate results and generate bar plots for a clear, high-level comparison of performance metrics.
🤖 Models Under the Microscope
1. DeepSeek-Coder-1.3B

Developer: DeepSeek AI
Description:

Specialized in code generation, trained on 8 trillion tokens, including 2 trillion dedicated to code.

Covers 80+ programming languages.

Based on LLaMA architecture, fine-tuned to follow programming instructions flawlessly.

2. Phi-2-2.7B

Developer: Microsoft Research
Description:

A small model with surprisingly powerful performance.

Trained on high-quality, curated data rather than raw web scrapes.

Excels in reasoning, understanding, and educational code tasks.

3. Gemma-2B-IT

Developer: Google
Description:

Lightweight, open-source, instruction-tuned version of the Gemini family.

Optimized for following user prompts accurately.

Perfect for generating code from natural language descriptions.

4. Stable-Code-3B

Developer: Stability AI
Description:

Powerful open-source code model, trained for versatile code generation.

Supports multiple languages and frameworks.

Strong at both writing new code and understanding existing code snippets.
