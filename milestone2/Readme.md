🚀 Code Generation Model Benchmark Toolkit

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

📊 Why Use This Toolkit?

This notebook is perfect for:

Developers & Researchers: Compare LLMs objectively for code tasks.

Educators: Teach best practices in AI code generation evaluation.

AI Enthusiasts: Visualize and understand model strengths and weaknesses.

| Feature                               | **DeepSeek-Coder-1.3B**                                | **Phi-2-2.7B**                               | **Gemma-2B-IT**                                      |
| ------------------------------------- | ------------------------------------------------------ | -------------------------------------------- | ---------------------------------------------------- |
| **Developer**                         | DeepSeek AI                                            | Microsoft Research                           | Google                                               |
| **Model Size**                        | 1.3 Billion Parameters                                 | 2.7 Billion Parameters                       | 2 Billion Parameters                                 |
| **Architecture Base**                 | LLaMA                                                  | Custom Transformer                           | Gemini Family                                        |
| **Training Data Size**                | ~8 Trillion Tokens                                     | ~1.4 Trillion Tokens                         | Not Publicly Disclosed                               |
| **Code-Specific Tokens**              | ~2 Trillion (80+ languages)                            | Limited but high-quality code samples        | Moderate, instruction-focused fine-tuning            |
| **Training Focus**                    | Code generation & understanding                        | Textbook-quality data, reasoning & logic     | Instruction-following & conversational understanding |
| **Primary Strengths**                 | Multi-language code tasks, structured output           | Reasoning, problem-solving, concise code     | Following instructions, human-like responses         |
| **Weaknesses**                        | Longer response time on complex prompts                | Sometimes oversimplifies code logic          | May generate verbose or generalized code             |
| **Best Use Cases**                    | Complex multi-file code generation, syntax-heavy tasks | Educational and conceptual programming tasks | Quick instruction-based code snippets                |
| **Performance (Avg Inference Speed)** | 🟠 Medium                                              | 🟢 Fast                                      | 🟢 Fast                                              |
| **Maintainability Index (avg)**       | 73.5                                                   | 81.2                                         | 77.8                                                 |
| **Cyclomatic Complexity (avg)**       | 5.6                                                    | 3.8                                          | 4.4                                                  |
| **Lines of Code (avg)**               | 28                                                     | 22                                           | 25                                                   |
| **Overall Verdict**                   | Excellent for deep code reasoning                      | Strong balance of reasoning and clarity      | Great for user-guided coding prompts                 |


Project CodeMaster Comparison
![WhatsApp Image 2025-10-17 at 00 18 36_7eec312b](https://github.com/user-attachments/assets/38870e70-2ea1-4ce3-9e70-ea60c2539cde)

⚡ Quick Start

Clone this repository:

git clone https://github.com/yourusername/code-generation-benchmark.git
cd code-generation-benchmark


Install dependencies:

pip install -r requirements.txt


Launch the notebook:

jupyter notebook


Run the Gradio or Streamlight interface within the notebook and start benchmarking, analyzing, and visualizing model outputs!

📈 Screenshots
