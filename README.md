This repository contains the code and results of article “Serotonin reduces belief stickiness,” by Vasco A. Conceição, Frederike H. Petzschner, David M. Cole, Katharina V. Wellstein, Daniel Müller, Sudhir Raman, and Tiago V. Maia. This article is available, as a preprint, at https://www.biorxiv.org/content/10.1101/2023.12.08.570769v1. 

The code is in zip file nbimd_code.zip. The results are in 45 zip files (nbimd_article_results.zip.001 through nbimd_article_results.zip.045) in folder nbimd_article_results. 

The code can be run without the results files, as the code generates the results. However, portions of the code take a very long time to run (on the order of days or weeks, in a regular laptop as of 2024). The results files therefore contain all intermediate results in the code pipeline; using these files makes it possible to run the separate portions of the code pipeline without running the entire pipeline.

To run the code, please follow these steps:
1.	Ensure that you have MATLAB, R, and SPSS installed, as the code uses these software packages.
2.	Download and extract file nbimd_code.zip.
3.	Read the documentation in file nbimd_code/info.txt and in the code’s master script, nbimd_code/shellmdl_master.m.
4.	Configure files nbimd_code/config/shellmdl_set_main_paths.m and nbimd_code/config/shellmdl_set_analysis_options.m following the instructions contained therein.
5.	Run the code’s master script, nbimd_code/shellmdl_master.m.

Note that some antivirus software (e.g., Norton) will remove the files with extension “mexw64” in step #2. These files are precompiled C files that are necessary to run portions of the code. If your antivirus software removes these files, you will not be able to run those portions of the code, unless you compile the corresponding files. You may also be unable to run these precompiled files if you are not using a 64-bit version of Microsoft Windows. For difficulties with these files, or for any other difficulties running the code, please contact Vasco A. Conceição at vasco.conceicao7@gmail.com.

If you want to use the results files, please follow these steps:
1.	Download and extract the 45 zip files in folder nbimd_article_results. After you have these 45 zip files, to extract them in Windows, you will need to use a program that can handle split zip files (e.g, 7-zip, which is free). You should select the first file (nbimd_article_results.zip.001) for extraction; the software will automatically also extract the remaining files. To extract these files in macOS, you should first run the following command in your terminal:  "cat nbimd_article_results.zip.* > merged_article_results.zip"; then, you should use the resulting file, merged_article_results.zip, to perform the extraction.
2.	After you have extracted the files, configure file nbimd_code/config/shellmdl_set_analysis_options.m so that the code loads the results that serve as input for the portion of the code that you want to run.
