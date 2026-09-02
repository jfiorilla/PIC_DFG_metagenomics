## TLDR
GC3F provided a md5sums file and a check script in each sub-project INFO folder. I ran the script as they suggested directly in terminal: `bash check_downloads.sh` and can confirm that all files matched/were not corrupted. 

## Log
Tried to use Brooke's code for computing md5sums but did not work
- [md5check.txt](https://github.com/jfiorilla/PIC_DFG_metagenomics/blob/5bf5fb617679b3a80b36e0aff3753b45b5ae4c1a/bash-scripts/md5check.txt)
- could be because of error in double `#!/bin/bash` 

Looked at files provided by GC3F and saw they already have a md5sums file so did some more digging in the INFO directory

The `check_downloads.sh` is provided code to run a checksums, copied necessary unity sbatch parameters but did not work
- error related to not finding INFO/md5sums.txt folder
- code says it can work from any directory, but unity seems to be confused

Ran check_downloads as a bash command in terminal (logged into unity to access files but not using computing capacity) and it's working
- slow but working with "live" feedback as script is running through files

Confirmed all files in 10604 were transferred without corruption
- also checks all the fastqc files

For 10605 tried again to combine the provided code and the sbatch parameters, this time including setting the sbatch directory to 10605/INFO 
- same error not finding INFO/md5sums.txt folder

This time I deleted the GC3F code about finding the directory and just added a specific line of code to navigate to the sequencing files 
- [md5check-10605.txt](https://github.com/jfiorilla/PIC_DFG_metagenomics/blob/5bf5fb617679b3a80b36e0aff3753b45b5ae4c1a/bash-scripts/md5check-10605.txt)
- working but just as slow I think
- used `tail -F slurm-checksum-63633790.out` to watch readouts in terminal (number is unity job ID)
- can also check file on unity browser to monitor 

Confirmed all files in 10605 were transferred without corruption
- read out saved as file `checksum-63633790.out`

Not sure if it's worth remaking the script with sbatch parameters if not significantly faster; will likely just navigate to the appropriate INFO folder and run bash command directly in terminal for remaining folders
- deleted the `md5check-10605.txt` and `checksum-63633790.out` files from unity

Confirmed all files in 10606 were transferred without corruption

Confirmed all files in 10607 were transferred without corruption

Confirmed all files in 10608 were transferred without corruption