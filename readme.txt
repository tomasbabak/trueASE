

Background:


Quantifying ASE of individual genes was done using two commonly applied approaches: 1) a binomial test with null expectation set to reflect overall expression from each species (ref babak et al nat gen), and 2) a negative binomial test (ref edgeR). It was observed, however, that both approaches yielded highly significant p-values with nearly all expressed genes under ASE (p<0.01). It can be argued that high sequencing depth, as applied here with most genes detected with thousands of sequencing reads, provides high power to detect minute differences in allelic expression. The negative binomial test relies on biological replicates to estimate variation that is factored into the p-value. In data we generated here, this robust replication supports the argument that we are powered to detect even very small differences. However, both of the statistical approaches assume that there are no technical biases between the two alleles. edgeR and DEseq were developed to sample the same gene across conditions where this assumption is likely true. An analysis of previous work in mouse inbred hybrids (ref nat genetics 2015 babak et al) and hybrid yeast (Ref carlo and hunter riboprofiling paper) we observed that sampling ASE at two polymorphic sites in the same mouse exon or two polymorhic sites in the same yeast ORF had a suprisingly high degree of disagreement. Priming and amplification differences during library construction due to allele-specific sequence differences may be the cause. Since these differences reproducibly yield the same number of sequencing reads from each allele, variation in observed ASE across samples is low even though the actual degree of ASE may not be known. We reasoned that, as long as the two polymorphic sites were independently sampled (i.e. by separate RNAseq fragments), the frequency with which they agree on direction of ASE does in fact reflect presence/absence of ASE. Taking all sites separated by a distance that exceeds the fragment lenght (ensuring they are independently sampled) we observed that disagreement is function of sequencing depth and the minimum level of measured ASE at each site. Disagreement was much more frequent than predicted using binomial test and strongly replicated between mouse and yeast. We formalized these observations into a mathematical model that we make available through easy-to-use perl and matlab functions (ref: https://github.com/tomasbabak/trueASE).



trueASE is a perl script. Usage is displayed when executed with no options or inputs (i.e. type: ./trueASE)

The matlab code can operate over double arrays.




