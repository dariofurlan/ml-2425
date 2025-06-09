# Promoter Prediction with DNABERT and DNABERT-2: A Reproduction and Analysis

**Authors**: Dario Furlan, Nicolò Raccichini  
**Date**: June 8, 2025

# Introduction
In recent years, researchers have begun to apply techniques from natural language processing (NLP) to genomic data. The key idea is that DNA, much like human language, can be represented as a sequence of symbols that carries information. Among the models inspired by this idea, **DNABERT** [^1] stands out as one of the first to treat DNA as a “language”, using the Transformer architecture originally designed for textual data. In this approach, DNA sequences are broken into overlapping fragments of fixed length called *k-mers*, which serve as the basic units or “words” for the model.

This analogy between language and DNA opens new possibilities for understanding complex biological mechanisms. One important application is **promoter prediction**, the task of identifying regions in the DNA that initiate gene transcription. Promoters act as on/off switches for genes, and knowing where they are helps us understand how genes are regulated. This project focuses on evaluating the performance of DNABERT and its improved version, **DNABERT-2** [^2], in this specific task.

To guide our exploration, we will address the following key points, each building upon the previous:

1. First, we explain how DNABERT is designed and why it outperforms older models.  
2. Next, we examine the main innovations introduced in DNABERT-2.  
3. Then, we introduce the biological concept of promoters and discuss their relevance to gene regulation.  
4. Finally, we replicate DNABERT's promoter prediction experiment using Python, applying theory to practice.

Through this structure, we aim to develop a clearer understanding of how Transformer-based models are adapted for genomic data and why they offer advantages over traditional machine learning techniques. To support this analysis, we first provide background on DNA, genes, and transcription, gradually introducing the biological concepts that motivate the use of these models.

[^1]: Ji, Y., Zhou, Z., Liu, H., & Davuluri, R. V. (2021). DNABERT: pre-trained Bidirectional Encoder Representations from Transformers model for DNA-language in genome. *Bioinformatics*, 37(15), 2112–2120. https://doi.org/10.1093/bioinformatics/btab083  
[^2]: Zhou, Z., Ji, Y., Liu, H., & Davuluri, R. V. (2024). DNABERT-2: Efficient Foundation Model and Benchmark For Multi-Species Genome. https://arxiv.org/abs/2306.15006

## Results

| Dataset | MCC (ours) | MCC (ref.) | Error |
|---------|------------|------------|-------|
| all     | 90.65 %    | 90.48 %    | 0.17  |
| notata  | 92.80 %    | 93.05 %    | 0.25  |
| tata    | 62.05 %    | 61.56 %    | 0.49  |

## License

MIT © 2025 Dario Furlan, Nicolò Raccichini