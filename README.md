# pcawg-infrastructure-paper

This Jupyter notebook contains the beginnings of our analysis code for the [PCAWG](https://dcc.icgc.org/pcawg) infrastructure paper.  This paper describes our efforts to run the core analysis for the project, namely the alignment workflow with 3 variant calling workflows.  We built various infrastructure components that let us do this in a distributed way across many (14) cloud and HPC environments.

The main text of the paper is currently in a private Google document and will be shared with authors/contributors.  This notebook will be used to generate our figures. There may be some additional scripts in this repository if things don't work well with Python notebooks.

## Install

You can find out how to install Jupyter [here](http://jupyter.readthedocs.org/en/latest/install.html) but I found it easier just to use Anaconda to install everything for me (the 3.x version).  See [Anaconda's](https://www.continuum.io/downloads) website.

You can also setup an environment before running jupyter using something like:

    conda create -n python3 python=3.5 anaconda
    source activate python3

If you forgot the conda environment you setup previously use the below to list them:

    conda info --envs

And then continuing on with the launch of jupyter below.

## Running

Change to this directory in your shell then execute:

    jupyter notebook

You can then load the `.ipynb` file in the web GUI that opens in your default web browser.

We're using Python 3.5 in this notebook.

## Data Files

### Metadata File

Junjun provided a metadata JSONL dump file that includes timing information:

http://pancancer.info/gnos_metadata/2016-04-08_02-02-09_UTC/donor_p_160408020209.jsonl.gz

Find it in these files (split to avoid size limits by Github):

* [donor_p_160408020209.1.jsonl.gz](donor_p_160408020209.1.jsonl.gz)
* [donor_p_160408020209.2.jsonl.gz](donor_p_160408020209.2.jsonl.gz)
* [donor_p_160408020209.small.jsonl.gz](donor_p_160408020209.small.jsonl.gz): a smaller file for testing

### QC Summary File

This is a metadata QC summary file from the QC working group:

https://docs.google.com/spreadsheets/d/1zSs_hRQrCIBlUmPpDvyEwpJv3X4t8Y73s6ZRdkBkeI8/edit#gid=983410225

Checked in as:

* [PCAWG-QC_Summary-of-Measures_QC_Measures.tsv](PCAWG-QC_Summary-of-Measures_QC_Measures.tsv)

## TODO

* I think there are zero values (especially for BWA) that need to be excluded
* may need to consider each sample independently rather than aggregate timing info per donor's tumors
