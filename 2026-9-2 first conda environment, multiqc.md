Things I learned this morning:
- only code run in ipnyb is r; all the bash script is just included for posterity and is actually run in terminal ssh unity 
- downloaded vscode - think it will be a good place to edit bash scripts as opposed to textedit, connected to the same repo as this so will need to stay on top of commits etc
- need to create [conda environment](https://unityhpc.org/documentation/software/conda/) with packages - unity uses miniforge rather than miniconda

## Workflow
(in terminal ssh unity)
Load conda: `module load conda/latest`
Create environment: `conda create --name seqproc-env`
Code to activate: `conda activate seqproc-env`
Install multiqc: `conda install bioconda::multiqc`
Move to directory with fastqc files: `cd /scratch4/workspace/jade_fiorilla_student_uml_edu-rawseqpic/23LVKKLT3/10604/INFO/
- only works outside of directory that has fastqc html and zip files
- for 10604 I moved all .html and .zip out of separate folders but not necessary; just navigate to parent directory and multiqc will search for fastqc files
Run: `multiqc .`
Download multiqc_report.html and put in repo
- appears to actually have run multiqc on the fastp files not the fastqc
