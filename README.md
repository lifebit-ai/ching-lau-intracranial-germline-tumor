From the online methods (paper is attached – but methods details for analysis available on line)
https://www.nature.com/articles/nature13296#Sec3

A workflow to operate on the incoming exome data needs it seems these algorithms (first for discovery, and then for annotation):
Discovery
Atlas-SNP2 was used to identify somatic single-nucleotide variants in targeted exons34. Pindel was also applied to call small-to-medium size of insertions and deletions35. A minimum of 4 high-quality supporting reads and a minimum mutant allele fraction of 0.08 was required for mutation calling. 

1.	Atlas-SNP2 – somatic single nucleotide variants in targeted exons. Coded in Ruby - https://sourceforge.net/p/atlas2/wiki/Atlas-SNP/
2.	Pindel - https://academic.oup.com/bioinformatics/article/25/21/2865/2112044 -- link is broken in the paper but I found this here:
https://github.com/genome/pindel


Annotation
Somatic mutations and germline variants were annotated using information from publicly available databases, including dbSNP build 135 and variants from the 1000 Genome project.

 The pipeline (@Aaron Taylor) do we have this pipeline?  Can you provide us a link?
1.	integrates ANNOVAR to determine whether the observed amino acid changes have synonymous, non-synonymous, nonsense, or splice-site changing properties on the encoded proteins and https://github.com/WGLab/doc-ANNOVAR (found a 9year old github gist on how to install and use! https://gist.github.com/brentp/819611  Probably something newer available?
2.	SIFT, 
a.	https://sift.bii.a-star.edu.sg/#:~:text=SIFT%20%2D%20Predict%20effects%20of%20nonsynonmous%20%2F%20missense%20variants&text=SIFT%20predicts%20whether%20an%20amino,and%20laboratory%2Dinduced%20missense%20mutations.
b.	https://sift.bii.a-star.edu.sg/www/code.html
3.	PROVEAN (Protein Variation Effect Analyzer)http://provean.jcvi.org/index.php
4.	Polyphen-2 algorithms to predict the functional impact of somatic point mutations. https://github.com/hammerlab/vcf-annotate-polyphen
5.	Variants were further annotated with entries from the Catalogue of Somatic Mutation version 52 (COSMIC, http://www.sanger.ac.uk/genetics/CGP/cosmic/) to determine if the mutations were detected at previously reported hotspots.

