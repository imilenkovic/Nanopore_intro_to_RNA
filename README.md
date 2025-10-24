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
cd Share/input/mRNA
```

List contents of a `.pod5` file:

```bash
h5ls mESCs_Mettl3_WT_0.pod5 | head
```

Count the total number of groups/datasets:

```bash
h5ls mESCs_Mettl3_WT_0.pod5 | wc -l
```

Recursively inspect the structure:

```bash
h5ls -r mESCs_Mettl3_WT_0.pod5 | head
```

---

##  Explore Input Data (POD5)

Activate the correct environment and navigate to the input folder:

```bash
cd
conda activate nano24
cd Share/input
```

Inspect reads and metadata in a `.pod5` file:

```bash
pod5 inspect reads PAU73302_92617d95_c2e6b444_0.pod5 | head
pod5 inspect summary
```

---

##  Quality Check with NanoPlot

Run **NanoPlot** from the sequencing summary:

```bash
conda activate nano24
cd Share/input
NanoPlot --summary test_seq_summary.txt --loglength -o nanoplot_output
```

###  Output

NanoPlot produces:
- HTML summary reports  
- Various plots (read length distribution, quality vs. length, etc.)  
- Log-transformed and standard statistics  

All outputs are saved in the `nanoplot_output/` directory.

---

##  Adjust Configuration

To reduce CPU usage to 4 cores, run:

```bash
sed -i 's/cpus = 8/cpus = 4/g' conf/local.config
```

---

##  Documentation

Full documentation:  
[[https://biocorecrg.github.io/master_of_pores/](https://biocorecrg.github.io/master_of_pores/MOP4-dev/index.html)]
