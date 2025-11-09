# cell_to_sentence_cell_type_pred
cell_to_sentence(c2s) cell_type_prediction

from pathlib import Path

# Define the markdown content
md_content = """# AI Researches in Cancer Treatment using LLMs
*by Moses Wai‑Ming Wong | 4 min read*  

As a data scientist, I am fascinated by how AI can accelerate cancer research and treatment. Cancer remains one of humanity’s most complex and devastating diseases, affecting millions each year and burdening both healthcare systems and families. Despite decades of progress, many cancers still evade cure because of their ability to mutate, resist therapy, and vary across individuals.

AI offers a transformative path forward — analyzing massive biological datasets faster than any human, uncovering hidden patterns for early detection, personalizing therapies, and speeding up drug discovery. Together, these advances bring hope that AI could one day help end cancer’s long reign.

## New Frontier in AI‑Driven Cancer Research

Google Research recently released a breakthrough study using the Gemma v2 open‑source language model, fine‑tuned on over a billion tokens of transcriptomic data, biomedical text, and metadata. By combining single‑cell RNA sequencing with large language modeling, the system can predict how cells respond to treatments and identify cancerous cell types from biopsy‑scale data — offering new tools for discovery and diagnosis.

This work inspired my own experiments to reproduce and extend these results, exploring how such models could support researchers and clinicians in developing smarter, faster, and more adaptive cancer therapies.

## Genes as Language: A New Way to Teach AI Biology

Traditional LLMs learn by interpreting human language — sequences of words with meaning shaped by context. But what if we applied the same principle to genes? Each gene could be treated as a “token” whose expression level represents its importance within a cell, forming a biological sentence that describes the cell’s state.

By training an LLM on these “cell sentences,” we can teach it to infer relationships between gene activity and outcomes such as treatment response, cell identity, or cancer potential. This idea reframes biology as a language to be decoded — and positions AI not just as a computational tool, but as an interpreter of life’s code.

As data centers and AI research continue to scale, these models may soon help us understand the genome as fluently as language — unlocking new frontiers in precision oncology and the fight against cancer.

## Experimental Reproduction and Key Subtopics

This study reproduces Google Research’s recent work on AI‑driven cancer modeling using open‑source tools and models provided by Google. All required resources — including datasets, pretrained weights, and scripts — can be freely accessed on GitHub and Hugging Face. The reproduction explores five main subtopics:

1. Preprocessing Genetic Data  
2. Predicting Cell Type Based on Single‑Cell RNA Sequences  
3. Predicting Tissue Characteristics from Multi‑Cell Biopsies  
4. Fine‑Tuning Large Language Models (LLMs)  
5. Predicting Perturbation Responses  

## Preprocessing

The process begins at the hospital or clinic, where a patient’s tissue sample is collected. Each tissue contains many individual cells, which are then isolated, barcoded, and undergo RNA sequencing. The sequencing process produces a gene expression profile for every cell — essentially a long list of genes and their activation levels. These expression values represent how “active” each gene is, forming a biological signature unique to each cell.

To prepare this data for language‑model processing, genes are ranked by their expression levels and converted into a gene sequence — a “cell sentence.” Each sentence may contain hundreds of thousands or even millions of gene tokens, so a maximum sequence length is set to keep computations manageable.

The resulting dataset is further formatted to match the specific LLM in use. For single‑cell type prediction, for instance, the model can accept raw gene sequences or prompt‑formatted inputs, where biological data is embedded within a linguistic structure. This seamless blending of natural language and gene language allows the model to interpret cellular information in a way that bridges biology and linguistics.

## Results and Insights

In my experiments, I successfully reproduced the cell‑type prediction results with an accuracy of 83.3% — a strong outcome that validates the approach. The model can assist doctors and researchers in quickly identifying the nature of any given cell — whether it appears normal, suspicious, benign, or malignant.

Using a single NVIDIA A100 GPU, I fine‑tuned multiple models in under an hour, achieving robust and consistent performance. This demonstrates that cutting‑edge biomedical AI is no longer limited to large research labs — with open‑source tools and proper computation, it is accessible to hospitals, universities, and independent researchers seeking to better understand the gene sequences within their own datasets.

## Conclusion

This work highlights how open‑source LLMs and biological data modeling can bring powerful cancer research capabilities to a wider audience. By treating genes as language, scientists can leverage the same breakthroughs that revolutionized natural language understanding to decode the language of life itself. The results show that AI can meaningfully interpret cellular data, assist in diagnosis, and ultimately accelerate the discovery of personalized cancer therapies.
"""

# Define the output path
output_path = Path("/mnt/data/AI_Researches_in_Cancer_Treatment_using_LLMs.md")

# Write markdown to file
output_path.write_text(md_content, encoding="utf-8")

# Return path for download
output_path
