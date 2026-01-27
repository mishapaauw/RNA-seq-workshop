## bioDSC RNA-seq workshop website 

This repository contains the source files (`.qmd`) and rendered website (`docs/`) for the bioDSC workshop on RNA-seq. It should be live [here](https://mishapaauw.github.io/RNA-seq-workshop/). 

## How does it work?

Episodes are written in Quarto markdown files (`episodes/*.qmd`). `bash` commands are not executed by Quarto, while `R` code (e.g. for differential gene expression) is actually executed when the website is rendered. That means that you need a working installation of `R` with all the required RNA-seq packages installed (see episode `Setup`) to be able to render this website.  

## Associated materials

This workshop depends on a [Google Colab notebook](https://colab.research.google.com/drive/1jR2Og_qrUVg-VXNsfqJc5eEILcqHJYAC?usp=share_link) and on an [associated repository](https://github.com/mishapaauw/RNA-seq-workshop-materials) which contains some materials and data.

## TODOs

Content:

- An additional episode on running RNA-seq analysis on the Crunchomics cluster (using `sbatch` or Marc's pipeline).

Logistics:

- Move or fork this repository to the bioDSC organization.