## Three datasets to practice DESeq2 analysis

The plant science and neuroscience datasets are from [EMBL-EBI](https://www.ebi.ac.uk/gxa/experiments). The microbiology dataset is from [GEO](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE160187).

The corresponding count tables and experimental design files were downloaded and slightly simplified by wrangling in Microsoft Excel (sorry, I don't do everything in code!). As for the microbiology count table, this was cleaned with the following pretty long bash command:

```bash
grep -v '#' GSE160187_countTable.tsv | sed 's|/homes/jimmy.breen/bioinfoCore/191219_DavidO_RNAseq/2_star/||g' | sed 's/_PAO1_sorted.bam//g' | sed -E 's/[^[:space:]]*_S([0-9]+)/S\1/g' > GSE160187_countTable_cleaned.tsv
```

## The datasets

1. :corn: :seedling: **The Plant Scientist: maize plants infected with the fungus *Ustilago maydis***

    - Experiment ID: `E-CURD-40`
    - Experimental factors:
        - Treatment, with levels: `Ustilago maydis` and `none`
        - Timepoint, with levels: `0.5`, `1`, `2`, `4`, `6`, `8`, `12`, days after infection

2. :brain: :zap: **The Neuroscientist: different brain regions from patients with different psychiatric problems**

    - Experiment ID: `E-GEOD-78936`
    - Experimental factors:
        - `disease`, with levels: `normal`, `schizophrenia`, `bipolar disorder`
        - `brain_region`, with levels: `area 9`, `area 11`, `area 24`

2. :microbe: :microscope: **The microbiologist: *Pseudomonas aeruginosa* bacteria exposed to different concentrations of copper**

    - Experiment ID: `GSE160187`
    - Experimental factors:
        - `genotype`, with levels: `POA1` (wild-type bacteria) and `XEN41` (tetracyclin resistant bacteria)
        - `treatment`, with levels: `none`, `MIC/10`, `MIC` levels of copper
        - `timepoint`, with levels: `0`, `24`, `48`, `72` hours of incubation