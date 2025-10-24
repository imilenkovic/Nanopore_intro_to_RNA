
#  Master of Pores – Day 2 Basecalling & Mapping

##  Basecall your pod5 files with Dorado 

Navigate to the pre-processing directory:

```bash
cd ~/MOP4/mop_preprocess
```

Edit the  `params.yaml` file

Run the pipeline!

```bash
nextflow run mop_preprocess.nf -params-file params.yaml -with-singularity --nv -profile local -bg > demultiplexing.log
```

##  Basecall your pod5 files with Dorado 

Navigate to the pre-processing directory:

```bash
cd ~/MOP4/mop_preprocess
```

Edit the  `params.yaml` file

Run the pipeline!

```bash
nextflow run mop_preprocess.nf -params-file params.yaml -with-singularity --nv -profile local -bg > demultiplexing.log
```

## Explore the bam files with samtools 

Some useful commands: 

```bash
samtools view file.bam | wc –l 
samtools view –F 4 file.bam | wc –l 
samtools view –s 0.1 file.bam | wc –l

samtools view –H file.bam | less
samtools view –h file.bam > file.sam

samtools view –Sb file.sam > new_file.bam
```

## Predict isoform usage with Isoquant 

For each bam file we can assign reads to knwon isoforms:

```bash
IsoQuant/isoquant.py --reference references/chr19.fa --genedb references/chr19_annotation.gb --complete_genedb --bam MOP4/mop_preprocess/mouse_demux_trial/alignment/pod5---bc_1_s.bam --data_type nanopore -o isoquant_bc1
```

##  Documentation

Full documentation:  
[[https://biocorecrg.github.io/master_of_pores/](https://biocorecrg.github.io/master_of_pores/MOP4-dev/index.html)]
