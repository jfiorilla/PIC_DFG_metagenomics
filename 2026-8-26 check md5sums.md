## TLDR


## Log
Tried to use Brooke's code for computing md5sums but did not work
- md5check.txt
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

This time I deleted the GC3F code about finding the directory and just added a blanket line of code to navigate to the sequencing files 
- working but just as slow I think
- used `tail -F slurm-checksum-63633790.out` to watch readouts in terminal
- can also check file on unity browser to monitor 

Confirmed all files in 10605 were transferred without corruption
- read out saved as file 

Not sure if it's worth remaking the script with sbatch parameters if not necessarily faster; will likely just navigate to the appropriate INFO folder and run bash command directly in terminal for remaining folders