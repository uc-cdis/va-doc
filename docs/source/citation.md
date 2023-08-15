# GWAS pipeline configuration template  

The VADC GWAS pipeline uses several R scripts developed by the Genetic Analysis Center (GAC) at the University of Washington (https://github.com/UW-GAC/analysis_pipeline/tree/master/R) which are built around the GENESIS R package (Gogarten _et al._ 2019). Ancestry groups (Non-Hispanic Black, Non-Hispanic Asian, Non-Hispanic White, Hispanic) were assigned according to the HARE designations (Fang _et al._ 2019). Population principal components were estimated across all populations as described previously (Hunter-Zinck _et al._ 2020). A sparse Genetic Relatedness Matrix (GRM) was generated out to the third degree with the KING algorithm (Manichaikul _et al._ 2010).   

Markers with low frequency alleles (MAF, user- insert cut off) or low imputation quality were removed (user- insert cut off). The GENESIS package first runs a ‘null model’ of no association under the null hypothesis that each SNP has no effect. The null model includes the outcome phenotype (continuous outcomes are inverse normal transformed) and all covariates, including the first (user- insert PCs) population PCs as fixed effects while genetic relatedness is controlled as a random effect. The null model does not include any SNP genotype terms as fixed effects. Dichotomous outcomes are fit with a “binomial” family while continuous outcomes are fit as a “gaussian” family. Next, the parameters estimated by the ‘null model’ are used to run single marker associations, where SNPs are tested for association with the outcome in a computationally efficient manner. For dichotomous outcomes, the saddlepoint approximation (SPA) is applied to calibrate unbalanced case-control ratios similar to SAIGE (Zhou _et al._ 2018). Variants are annotated with closest gene(s) and dbSNP IDs by VEP release 105 (McLaren _et al._ 2016) and both the top 100 GWAS hits and those with a p-value < 5e-8 are curated.  

For details on user-specified GWAS workflow arguments and thresholds, please refer to the GWAS metadata file and insert thresholds in the placeholders. 

# References 

Fang H, Hui Q, Lynch J, Honerlaw J, Assimes TL, Huang J, Vujkovic M, Damrauer SM, Pyarajan S, Gaziano JM, et al. 2019. Harmonizing Genetic Ancestry and Self-identified Race/Ethnicity in Genome-wide Association Studies. _Am J Hum Genet_ __105__: 763–772. 

Gogarten SM, Sofer T, Chen H, Yu C, Brody JA, Thornton TA, Rice KM, Conomos MP. 2019. Genetic association testing using the GENESIS R/Bioconductor package. _Bioinformatics_ __35__: 5346–5348. 

Hunter-Zinck H, Shi Y, Li M, Gorman BR, Ji S-G, Sun N, Webster T, Liem A, Hsieh P, Devineni P, et al. 2020. Genotyping Array Design and Data Quality Control in the Million Veteran Program. _Am J Hum Genet_ __106__: 535–548. 

Manichaikul A, Mychaleckyj JC, Rich SS, Daly K, Sale M, Chen W-M. 2010. Robust relationship inference in genome-wide association studies. _Bioinformatics_ __26__: 2867–2873. 

McLaren W, Gil L, Hunt SE, Riat HS, Ritchie GRS, Thormann A, Flicek P, Cunningham F. 2016. The Ensembl Variant Effect Predictor. _Genome Biol_ __17__: 122. 

Zhou W, Nielsen JB, Fritsche LG, Dey R, Gabrielsen ME, Wolford BN, LeFaive J, VandeHaar P, Gagliano SA, Gifford A, et al. 2018. Efficiently controlling for case-control imbalance and sample relatedness in large-scale genetic association studies. _Nat Genet_ __50__: 1335–1341.
