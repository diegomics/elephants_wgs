# elephants_reseq
:elephant: :elephant: :elephant: :elephant: :elephant: :elephant: :elephant: :elephant: :elephant: :elephant:

#### Pipeline for the whole-genome resequencing analysis of ~70 [timber Asian elephants from Myanmar](https://elephant-project.science)
:construction: Under construction! :construction:

## Requirements:
* [Slurm](https://slurm.schedmd.com)
* [Singularity](https://sylabs.io)
* [Conda](https://docs.conda.io)

The pipeline is configured to use 24 CPUs and 64 GB of RAM

## Installation:
```bash
git clone https://github.com/diegomics/elephants_reseq
cd elephants_reseq
bash install_dependencies.sh
```
## Runnning the pipline:
* Edit `variables.cnf` file with the respective paths, values and parameters.
1) Run QC and filtering on Illumina NovaSeq paired-end _fastq_ files
```bash
bash 01.ReSeq_QC.Trim.sh
```
2) Index, map and deduplicate trimmed reads against a reference
```bash
bash 02.ReSeq_Map.Dedup.sh 
```
3) Call variants of the samples, merge and filter 
```bash
bash 03.ReSeq_VarCall.sh
```
