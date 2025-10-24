# Nanopore_intro_to_RNA
Introduction to dRNA sequencing and correponding analyses

#  Master of Pores – Day 1 Setup & Exploration

This guide walks through the first steps of exploring **Master of Pores** and inspecting example nanopore input data.


First - check if you have nextflow installed.

```
nextflow -version
```
If not, install it this way:
```
wget https://github.com/nextflow-io/nextflow/releases/download/v25.04.0/nextflow
chmod +x nextflow
mkdir -p ~/bin
mv nextflow ~/bin/
echo 'export PATH=$HOME/bin:$PATH' >> ~/.bashrc
```
---


##  Explore Input Data (pod5)

Navigate to the input directory:

```bash
cd ~/Share/data/mouse/pod5

```

List contents of a `.pod5` file:

```bash
 pod5 inspect reads | head
```

Count the total number of groups/datasets:

```bash
pod5 inspect summary mouse_mRNA.pod5```

##  Documentation

Full documentation:  
[[https://biocorecrg.github.io/master_of_pores/](https://biocorecrg.github.io/master_of_pores/MOP4-dev/index.html)]
