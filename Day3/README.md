## basecall modifications with modification-aware basecalling models 

Navigate to the pre-processing directory:

```bash
cd ~/MOP4/mop_preprocess
```

Edit the  `params.yaml` file

Run the pipeline!

```bash
nextflow run mop_preprocess.nf -params-file params.yaml -with-singularity --nv -profile local -bg > mod_basecalling.log
```

## To compare two epinano output files

```
Rscript scatterplot_script.R file_1.csv file_2.csv output.pdf
```


## Extract modification frequency per position with Modkit

```bash
modkit pileup CTR.bam modkit/CTR_m6A_pileup.bed --log-filepath CTR_m6A_pileup.log
```



