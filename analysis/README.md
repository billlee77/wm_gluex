Documentation for doing an analysis on the W&M HPC cluster:

First, setup your environment by sourcing the setup script

`source $WM_GLUEX/setup_custom.csh`

Next create a directory somewhere where you want to execute the DSelector code, for example, ~/myanalysis/

`mkdir ~/myanalysis/`

`cd ~/myanalysis/`

Now to process run the analysis you will be using significant resources (8 CPU threads and several GB of memory), so you should NOT do this on the login server vortex.sciclone.wm.edu.  Instead, you should create an interactive batch session where you will have access to more resources.  This can be done with the following command

`qlogin -t Nminutes 1:vortex:ppn=Ncores`

where 'Nminutes' is the time in minutes that you need and 'Ncores' is the number of threads you are using in your runSelector.C (for more information on these sessions see http://www.wm.edu/offices/it/services/hpc/using/jobs/index.php).

Once you are logged into the interactive batch session you can now execute your job 

`cd ~/myanalysis/`

`source $WM_GLUEX/setup_custom.csh`

`root -b -q runSelector.C`

When you are finished running your code, you can exit the interactive batch session with the `exit` command which will bring you back to the vortex login server.

