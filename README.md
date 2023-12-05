# Starship-Dynamics
Code and files that were used to locate starship mobility 
## Examining variation across Starship loci in different genomes
1. Retrieving flanks plus trunkated 5srRNA genes plus starship borders from select genomes. Combined sequences for 5s rRNA gene plus starship border+ trunkated 5srRNA + genomic flank into a single multiFASTA file ([5Splus5SplusBorders.fasta](/data/5Splus5SplusBorders.fasta)):
```bash
cat 5SrRNA.fasta 5SplusBorders.fasta>5Splus5SplusBorders.fasta
```
2. Find missing starship flank seqeuence in arcadia genome. FACET was used to align 5Splus5SplusBorders.fasta against arcadia genome:
```bash
FACET db_free Arcadia2_Final.fasta 5Splus5SplusBorders.fasta -nc -g
```
3. Retrieve flanks + border sequence from aracida genome. GGF file from FACET command was uploaded to IGV and left and right border + seqeunces were manually copied from browser to new FASTA file (Arcadia_Chr4_Flank_223516-2376697.fasta). Also included was the 5SrRNA sequence:
4. Resulting left and right border sequences where then searched against all assemblies using FACET:
```bash
for f in `ls MINION/*fasta`; do FACET db_free $f Arcadia_Chr4_Flank_223516-2376697.fasta -nc -g; done
```
