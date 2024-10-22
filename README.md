The polypyrimidine tract (PPT) is a pyrimidine-rich region of pre-messenger RNA (pre-mRNA) that promotes spliceosome assembly and guides intron removal during RNA splicing. It is typically located near the 3' splice site and is usually 15–20 base pairs long.

The R functions in this repository are predictive tools designed to identify and score PPTs within a given nucleotide sequence (A, C, G, T). The function for finding PPTs is optimized to detect the longest PPT based on the heuristic described by Corvelo et al. (2010), which includes the following criteria:

1. Both 3′ and 5′ ends must be pyrimidines;
2. No more than two contiguous purines are allowed;
3. Each purine segment (length L < 3) must be flanked by at least 4L pyrimidines, ensuring a minimum pyrimidine content of over 2/3, with both upstream and downstream pyrimidine segments of length ≥ L;
4. T(GT)_n stretches are allowed;
5. Minimum PPT length of 9 nucleotides or a uridine content ≥ 5.

The function for calculating the PPT strength score is based on the specific nucleotide composition of the sequence, using the following formula:

PPTscore = f(A)⋅(−2) + f(C)⋅2 + f(G)⋅(−2) + f(T)⋅3

Where:
f(A), f(C), f(G) and f(T) represent the frequency of adenine (A), cytosine (C), guanine (G), and thymine (T) (or uracil), respectively.

**References:**

Corvelo, A., Hallegger, M., Smith, C. W., & Eyras, E. (2010). Genome-wide association between branch point properties and alternative splicing. *PLoS Computational Biology*, 6(11), e1001016. https://doi.org/10.1371/journal.pcbi.1001016
