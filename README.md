# PMPrimer - Automatically design multiplex PCR primer pairs for diverse templates
> Software repo is : https://github.com/AGIScuipeng/PMPrimer
## Datasets of PMPrimer
1. 16S ribosomal RNA (rRNA) genes of Archaea
    13421 16S rRNA genes in Archaea were retrieved from the non-redundant reference dataset (SSURef 108 NR) in SILVA (release 108, accessed November 2022) [2]. After removing the sequences with degenerate base, 11757 remaining sequences were used as testing dataset for 16S rRNA genes. Taxonomic classification in phylum, class and order were used for evaluation of template coverage and taxon specificity in this dataset.

2. hsp65 (groEL2) genes of Mycobacteriaceae
    7188 RefSeq assemblies in Mycobacteriaceae family were retrieved from NCBI (accessed November 2022) [1]. Based on gene annotation, 12705 gene sequences suspected hsp65 were extracted from these genomes. After filter of low quality and redundant sequences, 1161 suspected hsp65 sequences were left. Gene clustering analysis was carried out based on sequence similarity and 578 hsp65 (groEL2) and 583 groEL1 sequences were identified eventually (Supplementary Figure 1). Finally, 6528 hsp65 genes corresponding to 578 non-redundant hsp65 sequences of 221 species were used as testing dataset.

3. tuf genes of Staphylococci
   3624 tuf gene sequences in Staphylococcus genus were retrieved from the European Nucleotide Archive of the European Bioinformatics Institute (ENA-EBI) database (Coding release, accessed August 2022) [17]. The low quality sequences (too short, too long, and redundant sequences) were filtered and the multiple sequence alignment of remain sequences were obtained by MUSCLE5. The distance matrix was obtained based on alignment and the unusual sequences were further filtered. Finally, 2547 tuf genes of 55 species in Staphylococcus genus were obtained for downstream analysis.


## Command In Paper

1. 16S ribosomal RNA (rRNA) genes of Archaea
   
   Archaea_16SrRNA.rep.mc.fasta needs to be extracted from Archaea_16SrRNA.rep.mc.fasta.zip to obtain
   
   Command in paper is : `pmprimer -f Archaea_16SrRNA.rep.mc.fasta -a threshold:0.85 gaps:1.0 merge primer2 tm:45.0 -e hpcnt:600 save`

> 
1. hsp65 (groEL2) genes of Mycobacteriaceae
   
   Command in paper is : `pmprimer -f Mycobacteriaceae_groEL2.filt.mc.fasta -a primer2 -e hpcnt:30 save`
> 
1. tuf genes of Staphylococci
   
   Command in paper is : `pmprimer -f Staphylococcus_tuf.filt.mc.fasta -a threshold:0.995 minlen:5 merge primer2 -e save`