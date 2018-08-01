# DivPop
This study used the MESA cohort individuals with genotype and expression data to generate cis-eQTLs and multi-ethnic predictors of gene expression and show that training set with ancestry similar to the test set is better at predicting gene expression in test populations, emphasizing the need for diverse population sampling in genomics. 
### MESA models are avaliable for download at [PredictDB](http://predictdb.org/) for use with PrediXcan and S-Predixcan.
- On the [PredictDB](http://predictdb.org/) page, click on `contributed/` and then `MESA-2018-05-v2/` to find the latest `.db` files. These models are filtered by `zscore_pval` < 0.05 and `rho_avg` > 0.1, see [here](https://s3.amazonaws.com/predictdb2/GTEx-V7_HapMap-2017-11-29_README.txt) for explanation of performance statistics in the `.db` tables. 
- Unfiltered models are in the `unfiltered_dbs/` directory above

#### Example of how to pull model statistics from a `.db` file with `sqlite3`
```sql
$ sqlite3 AFA_imputed_10_peer_3_pcs_2.db
--view table schema--
sqlite> .schema
--output predictive performance R2 statistics to R2_values.txt--
sqlite> .headers on
sqlite> .mode tabs
sqlite> .output R2_values.txt
sqlite> select gene, genename, test_R2_avg from extra;
sqlite> .quit
```

### cis-eQTL summary statistics can be found [here](https://www.dropbox.com/sh/f6un5evevyvvyl9/AAA3sfa1DgqY67tx4q36P341a?dl=0).

### For more details, see our [*BioRxiv* preprint](https://doi.org/10.1101/245761):
**Genetic architecture of gene expression traits across diverse populations**

Lauren S Mogil, Angela Andaleon, Alexa Badalamenti, Scott P Dickinson, Xiuqing Guo, Jerome I Rotter, W. Craig Johnson, Hae Kyung Im, Yongmei Liu, Heather E Wheeler
