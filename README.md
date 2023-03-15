```
_   _ _      _             _                         _  ______          _     _ _         ___   ___ _____  ______          _           _   
| | | (_)    | |           (_)                       | | | ___ \        | |   (_| )       /   | /   |  _  | | ___ \        (_)         | |  
| | | |_  ___| |_ ___  _ __ _  __ _    __ _ _ __   __| | | |_/ /__ _ ___| |__  _|/ ___   / /| |/ /| | |/' | | |_/ / __ ___  _  ___  ___| |_ 
| | | | |/ __| __/ _ \| '__| |/ _` |  / _` | '_ \ / _` | |    // _` / __| '_ \| | / __| / /_| / /_| |  /| | |  __/ '__/ _ \| |/ _ \/ __| __|
\ \_/ / | (__| || (_) | |  | | (_| | | (_| | | | | (_| | | |\ \ (_| \__ \ | | | | \__ \ \___  \___  \ |_/ / | |  | | | (_) | |  __/ (__| |_ 
 \___/|_|\___|\__\___/|_|  |_|\__,_|  \__,_|_| |_|\__,_| \_| \_\__,_|___/_| |_|_| |___/     |_/   |_/\___/  \_|  |_|  \___/| |\___|\___|\__|
                                                                                                                          _/ |              
                                                                                                                         |__/               
 ```
 # Overview
This GitHub repository contains a Jupyter notebook for analyzing the taxonomy of reads from the microbiome of the Georiga Aquarium Ocean Voyager exhibit using [QIIME 2](https://qiime2.org/).

# Requirements
To use the notebook in this repository, you will need 
- A[QIIME 2 ```conda``` environment](https://docs.qiime2.org/2023.2/install/native/).
- [Git Large File Storage (LFS)](https://git-lfs.com/).

# Data
FASTQ sequences (SRA accession PRJNA417313, [original publication](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5930379/)) were downloaded from the NCBI Sequence Read Archive (SRA) after installing the [SRA toolkit](https://github.com/ncbi/sra-tools) and [Entrez Direct](https://www.ncbi.nlm.nih.gov/books/NBK179288/) and running the command
```
esearch -db sra -query PRJNA417313  | efetch | cut -d ',' -f 1 | grep SRR | xargs fastq-dump --split-files
```
Data was downloaded to a folder named "ov_data" in the repository root directory. These FASTQ files are untracked due to size.

# Folder Structure
- qiime_analysis: contains qiime_analysis.ipynb analysis notebook and related output files from QIIME 2.

# Usage
To generate the taxonomy bar plot using QIIME 2:
- Install [Git LFS](https://git-lfs.com/) to download "qiime_analysis/paired-end-demux.qza".
- Install [QIIME 2 locally](https://docs.qiime2.org/2023.2/install/native/)
- Activate the QIIME 2 ```conda``` environment using the environment’s name:: ```conda activate qiime2-2023.2```
- Launch ```jupyter notebook``` or ```jupyer lab```
- Run the qiime_analysis.ipynb Jupyter notebook
