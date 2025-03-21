This Repository contains the code and results for article “Serotonin reduces belief stickiness,” by Vasco A. Conceição, Frederike H. Petzschner, David M. Cole, Katharina V. Wellstein, Daniel Müller, Sudhir Raman, and Tiago V. Maia. This article is available, as a preprint, at https://www.biorxiv.org/content/10.1101/2023.12.08.570769v1. 

The code is in zip file nbimd_code.zip. The article results are in 45 zip files (nbimd_article_results.zip.001 through nbimd_article_results.zip.045) in folder nbimd_article_results. 

The code can be run without the article-results files, as the code analyzes the data to generate the results. However, portions of the code take a long time to run (on the order of days or weeks, in a regular laptop as of 2024). The results files therefore contain all intermediate results in the analysis pipeline; using these files makes it possible to run portions of the pipeline without running the entire pipeline (see the "Demo" section below).

-------------------------------------------------------------------------
Before trying to run the code, please see the following sections below:
- System requirements;
- Installation guide;
- Instructions for use;
- Demo.

If you experience any difficulties, please contact Vasco A. Conceição at vasco.conceicao7@gmail.com.

-------------------------------------------------------------------------
System requirements

To run the full analysis pipeline, MATLAB, R, jamovi, and SPSS need to be installed. 
We used MATLAB R2015a and R2019a, RStudio 2023.12.1+402 (R version 4.0.5130), jamovi version 1.6.23, and IBM SPSS Statistics 22. The analysis pipeline can be run on a regular computer using this software and a 64-bit version of Microsoft Windows (although, as noted above, portions of the code take a long time to run in regular computers). 

-------------------------------------------------------------------------
Installation guide 

After having installed the software mentioned in the previous section, you can install the code contained in this Repository by downloading and extracting file nbimd_code.zip. This should only take a few minutes, although the precise duration will depend on your internet speed and hardware.

Please note that some antivirus software (e.g., Norton) may remove the files with extension “mexw64.” These files are precompiled C files that are necessary to run portions of the code. If your antivirus software removes these files, you will not be able to run those portions of the code, unless you compile the corresponding files. You may also be unable to run these precompiled files if you are not using a 64-bit version of Microsoft Windows. For difficulties with these files (or for any other difficulties running the code), please contact Vasco A. Conceição at vasco.conceicao7@gmail.com.

-------------------------------------------------------------------------
Instructions for use

1. Read the documentation in file nbimd_code/info.txt and in the code’s master script, nbimd_code/shellmdl_master.m;
2. Configure files nbimd_code/config/shellmdl_set_main_paths.m and nbimd_code/config/shellmdl_set_analysis_options.m, following the instructions contained therein;
3. Run the code’s master script, nbimd_code/shellmdl_master.m.

-------------------------------------------------------------------------
Demo

If you want to run the code using the article-results files, please follow these steps:
1. Download and extract the 45 zip files in folder nbimd_article_results. After you have downloaded these files, to extract them in Windows, you will need to use a program that can handle split zip files (e.g., 7-zip, which is free). You should select the first file (nbimd_article_results.zip.001) for extraction; the software will automatically also extract the remaining files.
2. After you have extracted the files, configure file nbimd_code/config/shellmdl_set_analysis_options.m so that the code loads the results of interest. You can opt to load all article results or, instead, load only those that are needed to run a specific portion of the code. For example, you can opt to load the output files from the data-preprocessing pipeline to then run the behavioral-analysis pipeline, by configuring the respective code lines accordingly: <br>
    <br>
    options.run.datapreprocessing = 0; <br>
    options.load.datapreprocessing = 1; <br>
    options.save.datapreprocessing = 0; <br>
    options.overwrite.datapreprocessing	= 0; <br>
    <br>
    options.run.behavioralanalysis = 1; <br>
    options.load.behavioralanalysis = 0; <br>
    options.save.behavioralanalysis	= 1; <br>
    options.overwrite.behavioralanalysis = 1; <br>

Output files, which will replicate the results of the portion of the analysis being run, will be saved in paths.resultsdir, as specified in nbimd_code/config/shellmdl_set_main_paths.m and nbimd_code/shellmdl_paths.m. Please note that whereas the data-preprocessing and behavioral-analysis portions should take only seconds to minutes to run, some portions of the pipeline, like the model-fitting one, can take days to weeks to run, in a laptop similar to the one that we used \[an Asus VivoBook 15 with Intel(R) Core(TM) i7-1065G7 CPU @ 1.30GHz 1.50 GHz processor, 8 GB of installed RAM, and Windows 11 64-bit Home\].
