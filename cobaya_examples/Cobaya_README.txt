This document contains the necessary steps to get the cobaya analysis for this project set up and running. Most of the details follow the documentation at https://cobaya.readthedocs.io/en/latest/

Installation:
There are several steps to installation. The first follow the instructions in https://cobaya.readthedocs.io/en/latest/installation.html:
-Before installation, install a working version of open-mpi (http://macappstore.org/open-mpi/), which can also be installed using homebrew on a mac. Then follow at the link above to install the python wrapper and check it is correctly installed. A working fortran compiler and version of python are also required. 
-next follow the instructions to pip install cobaya from the link above
-install the Cosmology packages for cobaya at /path/to/modules following https://cobaya.readthedocs.io/en/latest/installation_cosmo.html by running
cobaya-install cosmo -m /path/to/modules
-make sure the modified version of camb is compiled, including its python interface. Call its path /path/to/modified-CAMB/
This is all that is needed for installation, see details on running the analysis below.

Installation on the odyssey cluster:
On the odyssey cluster, installation is slightly different. A new python conda environment should be created. After loading Anaconda, gcc, and open-mpi with

module load Anaconda3/5.0.1-fasrc01
module load gcc/8.2.0-fasrc01 openmpi/4.0.1-fasrc01

create a new environment, load python 3.6, and install the python wrapper for open-mpi. Then pip install cobaya, install the cosmology modules the same way as above, and build the modified CAMB version as above. Once the conda environment has been set up (call it Cosmology), to run the software the following commands need to be run upon log in:

module load Anaconda3/5.0.1-fasrc01
source activate Cosmology
module load gcc/8.2.0-fasrc01 openmpi/4.0.1-fasrc01

Running Cobaya with CAMB:

