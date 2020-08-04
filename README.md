## What is in this repository?

1. `ref.fa` contains multiple DNA sequence alignment of hslU gene (ATP-dependent protease ATPase subunit HslU) on 4038 reference bacteria species.
2. Synonymous mutations have a higher rate of mutation and subject to homoplasy (convergent evolution and reversal). In this case, the third codon is preferred to be masked before any phylogenetic analysis. `ref_nothird.fa` is the resulting alignment after masking third codon positions in `ref.fa`.
3. `query.fa` contains multiple DNA sequence alignment of hslU gene (ATP-dependent protease ATPase subunit HslU) on 8 query bacteria species.
4. `query_nothird.fa` is the resulting alignment after masking third codon positions in `query.fa`.
5. `backbone_ml.nwk` is backbone tree on 4038 reference bacteria species. Branch lengths are in the unit of expected number of mutations per site and is estimated using a Maximum likelihood based method. In order to use this backbone in a distance based phylogenetic placement analysis, branch lengths have to be reestimated using the following two commands: 

`export OMP_NUM_THREADS=3

FastTreeMP -nt -nosupport  -nome  -noml -log true_me.fasttree.log -intree backbone_ml.nwk < ref.fa > true_me.fasttree`

