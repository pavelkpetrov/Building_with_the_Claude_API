# Building with the Claude API — Course Examples

My notebooks and exercises from the Anthropic course
[Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api).
Each notebook covers one topic from the course. The numeric prefix matches the course section.

## Contents

| Section | Notebooks | Topics |
|---------|-----------|--------|
| **001 – Accessing Claude** | `001_Accessing_Claude_*.ipynb` | Basic requests, multi-turn conversations, system prompts, temperature, controlling output (prefill, stop sequences) |
| **002 – Prompt Evaluation** | `002_Prompt_evaluation_*.ipynb` | Building eval datasets, model- and code-based grading, streaming responses |
| **003 – Prompt Engineering** | `003_Prompt_Engenering_prompting_exercise.ipynb` | Improving a prompt step by step and measuring the result with evals |
| **004 – Tool Use** | `004_tools*.ipynb`, `004_web_search_complete.ipynb` | Defining tools, multi-turn tool calls, streaming with tools, the text editor tool, the built-in web search tool |
| **005 – RAG & Agentic Search** | `005_RAG_Agentic_*.ipynb` | Chunking, embeddings (Voyage AI), a simple vector DB, BM25 lexical search, hybrid search |
| **006 – Claude Features** | `006_Features_Claude_*.ipynb` | Extended thinking, images, PDFs, prompt caching, code execution with the Files API |
| **MCP project** | `cli_project/` | A CLI chat app with an MCP server and client (documents via `@doc`, prompts via `/command`). See [`cli_project/README.md`](cli_project/README.md) |

### Supporting files

- `earth.pdf`: sample PDF for the PDF notebook
- `images.zip`: sample images for the image notebook
- `report.md`: sample document for the RAG chunking and search notebooks
- `streaming.csv`: sample dataset for the code execution notebook

## Running the notebooks

Most notebooks were written for **Google Colab** and read their settings with
`google.colab.userdata`, so add these secrets in Colab:

- `ANTHROPIC_API_KEY`: your Anthropic API key
- `CLAUDE_MODEL`: the model ID to use, for example `claude-sonnet-5`

The RAG notebooks (section 005) load their settings from a `.env` file with `python-dotenv`.
The embedding, vector DB and hybrid search notebooks also need `VOYAGE_API_KEY` for Voyage AI embeddings.

To run the Colab notebooks locally, replace the `userdata.get(...)` calls with environment
variables, then install the dependencies:

```bash
pip install anthropic voyageai python-dotenv
```