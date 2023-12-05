# Starship-Dynamics
Code and files that were used to locate starship mobility 
## Examining variation across Starship loci in different genomes
1. Retrieving flanks plus trunkated 5srRNA genes plus starship borders from select genomes. Combined sequences for 5s rRNA gene plus starship border+ trunkated 5srRNA + genomic flank into a single multiFASTA file:
```bash
cat 5SrRNA.fasta 5SplusBorders.fasta>5Splus5SplusBorders.fasta
```
