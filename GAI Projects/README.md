# Generative AI Projects

This folder contains six DSC 670 notebooks exploring prompt engineering, image generation, retrieval-augmented generation (RAG), and model fine-tuning. The notebooks are ordered by the original course weeks, from Week 2 through Week 7.

## Project index

| Project | Notebook | Topic | Overview |
| --- | --- | --- | --- |
| 1 | [Project1.ipynb](Project1.ipynb) | Invoice extraction with prompt engineering | Uses an OpenAI vision-capable model to transcribe an invoice PDF, then converts the transcription into schema-constrained JSON. The two-stage workflow emphasizes preserving source values and checking completeness and structure. |
| 2 | [Project2.ipynb](Project2.ipynb) | Vision generative AI | Generates a living-room image with Stable Diffusion XL, then edits that image with image-to-image diffusion. The notebook recommends comparing results with a second vision-generation interface using the same prompt. |
| 3 | [Project3.ipynb](Project3.ipynb) | Prompt engineering with chat models | Compares zero-shot and one-shot extraction of shoe orders from emails into JSON, then tests a worked-example chat prompt on an age word problem. |
| 4 | [Project4.ipynb](Project4.ipynb) | Apollo 11 article RAG chatbot | Scrapes and cleans the Apollo 11 Wikipedia article, splits it into section-aware chunks, indexes embeddings with FAISS, and answers grounded questions with a Qwen model. Includes a Gradio chat interface and discussion of limitations. |
| 5 | [Project5.ipynb](Project5.ipynb) | IMDb sentiment classification | Fine-tunes DistilBERT on a sample of the IMDb movie-review dataset for positive/negative sentiment classification, evaluates accuracy, and tests predictions on new reviews. |
| 6 | [Project6.ipynb](Project6.ipynb) | Parameter-efficient LLM fine-tuning | Fine-tunes Mistral-7B-Instruct with LoRA adapters on a sample of the Dolly instruction dataset using 4-bit quantization. Includes a short generation test and discussion of training limitations. |

## Running the notebooks

1. Open a notebook in Jupyter or VS Code and run its cells from top to bottom.
2. Install the libraries imported by that notebook. Dependencies vary by project; common packages include `torch`, `transformers`, `datasets`, `diffusers`, `openai`, `sentence-transformers`, `faiss-cpu`, and `gradio`.
3. Ensure you have an internet connection for downloading datasets, models, or the Wikipedia page. Large model downloads may require several gigabytes of free disk space.
4. Provide any required credentials when prompted or through environment variables. Projects 1 and 3 require an OpenAI API key; Project 2 may use an optional Hugging Face token for model downloads.

## Project-specific notes

- **Project 1:** The notebook downloads the invoice PDF when possible, but also contains a local PDF path. Update `PDF_PATH` if the fallback file is stored elsewhere. The notebook prompts for an OpenAI API key if `OPENAI_API_KEY` is not set.
- **Project 2:** Stable Diffusion XL is resource-intensive. A CUDA GPU or Apple Silicon with MPS is recommended; CPU execution may be slow. Generated images are saved under `stable_diffusion_outputs/`.
- **Project 3:** The notebook prompts for an OpenAI API key if `OPENAI_API_KEY` is not set. Model/API availability and pricing may change over time.
- **Project 4:** The notebook downloads the article and Hugging Face models at runtime. It can run with CPU, though inference is faster with a supported GPU. The final cell launches a Gradio interface.
- **Project 5:** The IMDb dataset is downloaded from Hugging Face. The notebook trains on a subset to keep the exercise manageable; training time depends on available hardware.
- **Project 6:** A CUDA-capable NVIDIA GPU is required for the notebook's 4-bit `bitsandbytes` training setup; Google Colab with a T4 GPU is suggested. The notebook installs several of its dependencies in a cell.

These notebooks are educational demonstrations. Model outputs and evaluation results depend on the software versions, hardware, remote datasets/models, and API services available when they are run.
