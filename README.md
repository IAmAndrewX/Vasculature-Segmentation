# Windows-Based Vasculature Segmentation Pipeline

This is an adapted Notebook for Vasculature Segmentation created by Michaël Bernier, developed for the Biosignals and Systems Analysis Lab. Using WSL2, it allows for the segmentation of brain vasculature of TOF and SWI scans from the beginning to the end.
It also resolves issues with the original notebook that exists, including the depreciation of get_data.

## Install and Setup
The pipeline is designed to be plug and play, however, there are some prerequisites before running the code.

### Installing WSL2 and FSL
This code takes advantage of the new --login-type operator in the Windows Subsystem for Linux. This, to my knowledge, is only available in WSL2. For instructions on installing WSL2 and FSL, please see here: https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FslInstallation/Windows
For instructions to upgrade WSL to WSL2, please see here: https://learn.microsoft.com/en-us/windows/wsl/install#upgrade-version-from-wsl-1-to-wsl-2

### CLEAR-SWI
If you plan to use the preprocessing for SWI images, you must get the executable for CLEAR-SWI. You can find them here: https://github.com/korbinian90/CompileMRI.jl/releases

### Python Libraries/dcm2niix
If you uncomment any pip installs in the notebook, it should install all required packages for you automatically. Do not forget to recomment them after, otherwise, the pip operation will try to run again and check for dependencies every time.


## Output Structure

Currently, the output structure goes:
```
root
|
|---subject
|   |input_files
|   |
|   |
|   └--out_folder
|   |   |outfile1
|   |   |outfile2
|   |   |...
|   |   └--vasc_scales
|   |   |  |VED_file1
|   |   |  |VED_file2
|   |   |  |...
|   |   |  |factor_analysis
|   |   |  |otsu_thresh
|   |   |  |VED_max

```
The project mainly uses absolute filepaths, as that is the main method of solving any calls to Linux.

## Common Errors with WSL

1. Exit Code 2147942408
    - This Exit Code indicates that your system does not have enough memory to activate an instance of WSL. This can sometimes be fixed by restarting your computer.

## Future of the Project

Although this code is originally made for Windows, the code can quite easily be adapted for MacOS or Linux. Future updates may add this functionality.

Furthermore, adjustments to processing pipeline may be made

## Citations
M. Bernier, S. C. Cunnane, K. Whittingstall. The morphology of the human cerebrovascular system, Human Brain Mapping 2018 (https://doi.org/10.1002/hbm.24337), Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)

K. Eckstein et al. Improved susceptibility weighted imaging at ultra-high field using bipolar multi-echo acquisition and optimized image processing: CLEAR-SWI, NeuroImage 2021 (https://doi.org/10.1016/j.neuroimage.2021.118175), MIT License

S.M. Smith. Fast robust automated brain extraction. Human Brain Mapping 2002 (https://doi.org/10.1002/hbm.10062)

M. Jenkinson, M. Pechaud, and S. Smith. BET2: MR-based estimation of brain, skull and scalp surfaces. In Eleventh Annual Meeting of the Organization for Human Brain Mapping, 2005.

M. Jenkinson and S.M. Smith. A global optimisation method for robust affine registration of brain images, Medical Image Analysis 2001.

M. Jenkinson, P.R. Bannister, J.M. Brady, and S.M. Smith. Improved optimisation for the robust and accurate linear registration and motion correction of brain images. NeuroImage 2002.

## Fun Stuff

@Author: Andrew Xie (mailto:andrew.xie@mail.mcgill.ca)
