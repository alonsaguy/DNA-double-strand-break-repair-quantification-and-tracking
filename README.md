# DNA-double-strand-break-repair-quantification-and-tracking
This repository contains the code used in this paper.

Please make sure to cite it in case of use - [link to arXiv](https://www.biorxiv.org/content/10.1101/2024.08.23.609327v2.abstract)


This code utilizes 3D imaging flow cytometry to track DNA dynamics at the population level with single-cell sensitivity in high throughput. The code processes couple of .cif files, beads and cells, collected togther in the ImageStream and separated using the IDEAS software. The code is devided into 6 sections: Installing dependencies, Choosing parameters, Converting CIF to TIF, Calibration, Localization, and Plotting. Section #1 & #2 run once, while Section #3-#6 execute for each bead-cell pair from the same sample).

**Installation guide:**
Run section #1 in Google Colab to install dependencies.
Typical installation time: 3m
Tested with Python 3.11. Requirements file attached in GitHub for local installation.

**Demo Run Instructions:**
1. Look for the demo data_files at [link](link_to_files) and upload the .cif files and the .txt files to the same directory in Google Drive.
2. Run section #1 to install dependencies includes the installation of relevant programs, and the loading and execution of all functions required for the analysis.
3. Specify the run type in section #2. Namely, where the data is located (the folder in Google Drive), whether the calibration should be made by the beads or the cells, etc. Please make sure to check the convert_cif_to_tif parameter and the create_calibration_map parameter for this demo.
4. Run section #3 to generate the tif files of the data files. At the end of this step, a directory with the name of each cif file should be created in the specified data_path. Additionally, each directory will contain two tif files - one for each recording channel.
5. Run section #4 to generate the calibration maps for 3d localization. If you specified '2D' detection mode, running this cell is not required. At the end of this step, some plots showing the quality of the calibration will be generated.
6. Run section #5 to localize the loci in each channel for all files in the data_path directory. At the end of this step, some visualizations of the 3D localization statistics will be generated.
7. Run section #6 to calculate the 3D distances between the loci of each captured cell and generate visual plots. Additionally, a .csv file containing localization properties for all analyzed cells is exported to the analysis folder.

Expected run time: Analyzing cells only ~10-15min; Analyzing cells and beads ~40-45min
