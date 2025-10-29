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
modkit pileup Share/data/mouse/output/dorado_m6A_drach/mouse_drach_trial/alignment/pod5---bc_1_s.bam modkit/CTR_m6A_pileup.bed --log-filepath modkit/CTR_m6A_pileup.log
```


## Extract modification frequency per read with Modkit

```bash
modkit extract full Share/data/mouse/output/dorado_m6A_drach/mouse_drach_trial/alignment/pod5---bc_1_s.bam --num-reads 1000 test_modkit_full.txt
``` 

