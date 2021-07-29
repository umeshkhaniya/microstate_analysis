# Microstate Analysis of Protein
This is the tutorial for microstate analysis in the Monte Carlo Sampling. Main idea of this tool is novel way of understanding the charge states of protein molecules. During the MCCE pdb run,  millions of microstate are generated and goal here is to analyse microstates and find out the right protonation state for Molecular Dynamics simulation. In this tutorial, small system 4lzt at pH = 5 is taken for the demo purpose. 

# Introduction:
Proteins are dynamic objects and it is well established that they exist in a distribution of conformations.  Conformationaion distributions are required for function, but they are also inevitable given the low barriers to many of the motions proteins can undergo. Thus, a protein with N atoms has 3N-6 vibrational modes to generate the conformational flexibility. 



## Input File:
- head3.lst 
- ms_out file
- sum_crg.out

## Script requirement:
  - ms_analysis.py: This script loads the input file.
  - microstate_analysis.ipynb : This is for post processing.
  
  
 
