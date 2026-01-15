# Fine-tuned GPT-based foundation models effectively reconstruct bacterial transcriptional regulatory networks from literature

## Abstract

**Introduction:** The synthesis of RNA from DNA, named *transcription*, is a primary process in cells. A well-established approach for studying the mechanisms by which transcription is regulated in bacteria is the analysis of *transcriptional regulatory networks* (TRNs). These networks provide a global view of how gene expression is regulated to allow the cell to respond to environmental changes. The study of TRNs of bacteria has driven relevant areas, such as antimicrobial resistance. The traditional way to reconstruct these networks is by manual curation from the literature, which is an accurate process, but also demanding and time-consuming. These limitations have resulted in a shortage and incompleteness of bacterial TRNs.

**Methods:** Here, we present a novel ensemble model approach using two GPT-based foundation models (LLaMA and GPT-4o mini) to effectively reconstruct TRNs from the literature. We applied a supervised fine-tuning strategy with sentences from *Escherichia coli* literature to train models to predict the type of regulatory effect between a transcription factor and a regulated element (gene/operon). To evaluate the performance of reconstructing a curated TRN, we used 264 complete articles of *Salmonella* Typhimurium, a pathogen of clinical interest.

**Results:** With the test data, both models obtained significant performance (F1-Score > 0.87, Matthews correlation coefficient > 0.82). For the curated TRN reconstruction, an ensemble approach using the prediction agreement of both models correctly reconstructed up to 80% of the TRN. We applied the approach to reconstruct large *Salmonella* TRN using the up-to-date available literature on transcriptional regulation of this bacterium (2278 articles). This network was described with network metrics and compared to existing biological knowledge.

**Discussion:** Our approach overtook the performance of prior works, not only classifying if an interaction is true, but also predicting the effect of the interaction. The analysis of the TRN of the 2278 articles showed the effectiveness of our approach to reconstruct TRNs of diverse bacteria, as the network aligns with biological knowledge. Thus, our work may support the study of bacteria of biological and clinical interest.

## Data sets for the study

### Data set for fine-tuning

For fine-tuning the GPT models and comparing our results with previous work, we leveraged the data set of sentences of *E. coli* literature presented in Varela-Vega et al. (2024). The data set comprises 1562 sentences in the appropriate format for fine-tuning the GPT models.

[https://github.com/laigen-unam/GPT-trn-reconstruction/blob/main/Data_sets/Fine_tuning](https://github.com/laigen-unam/GPT-trn-reconstruction/blob/main/Data_sets/Fine_tuning)

### Data set to evaluate TRN reconstruction

As our approach aims to reconstruct TRNs from complete articles of several bacteria, we evaluated the best fine-tuned models of GPT-4o mini and LLaMA 3 for the extraction of a TRN of *Salmonella* using the same 264 curated articles used in prior work. We also used the set of 909 unique interactions (TF-regulated element-effect) manually extracted from those articles to evaluate the extraction of the best GPT-4o mini and LLaMA 3 models.


- [Curated TRN of 264 articles](https://github.com/laigen-unam/GPT-trn-reconstruction/blob/main/Reconstructed_TRNs/TRN_reconstruction_evaluation/curated_data_set_264.tsv)
- [⁠Data set of 264 articles for evaluation](https://github.com/laigen-unam/GPT-trn-reconstruction/blob/main/Reconstructed_TRNs/TRN_reconstruction_evaluation/dataset_264_articles_for_evaluation.tsv)


## Reconstructed Salmonella TRN with 264 articles
- [GPT-4o mini](https://github.com/laigen-unam/GPT-trn-reconstruction/blob/main/Reconstructed_TRNs/TRN_264_articles/Reconstructed_TRN_264_GPT.tsv)
- [LLaMA 3 8B](https://github.com/laigen-unam/GPT-trn-reconstruction/blob/main/Reconstructed_TRNs/TRN_264_articles/Reconstructed_TRN_264_LLaMA.tsv)

## Reconstructed Salmonella TRN with 2278 articles

- [Ensemble model approach predictions](https://github.com/laigen-unam/GPT-trn-reconstruction/blob/main/Reconstructed_TRNs/TRN_2278_articles/Ensemble_predictions_TRN_2278.tsv)
- [Reconstructed Salmonella TRN](https://github.com/laigen-unam/GPT-trn-reconstruction/blob/main/Reconstructed_TRNs/TRN_2278_articles/Reconstructed_TRN_2278.csv)

## References

Varela-Vega, A., Posada-Reyes, A.-B., and Méndez-Cruz, C.-F. (2024).  
   *Automatic extraction of transcriptional regulatory interactions of bacteria from biomedical literature using a BERT-based approach*.  
   **Database**, 2024, baae094.  
   https://doi.org/10.1093/database/baae094


