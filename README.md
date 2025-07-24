# Microstate Analysis of a Protein
This is a tutorial for microstate analysis in Monte Carlo Sampling.
The main idea of this tool is to provide a novel way of understanding the charge states of protein molecules. During the MCCE PDB run, millions of microstates are generated. The goal here is to analyze these microstates and determine the correct protonation state for Molecular Dynamics simulations. In this tutorial, a small system-4lzt at pH 5—is used for demonstration purposes.

# Introduction:
Proteins are dynamic molecules, and it is well established that they exist in a distribution of conformations. These conformational distributions are essential for function and are also inevitable due to the low energy barriers associated with many protein motions. A protein with N atoms has 3N−6 vibrational modes that contribute to its conformational flexibility.

Monte Carlo sampling in MCCE uses the Metropolis–Hastings algorithm to evaluate the probability distribution of microstates. A microstate step involves flipping the conformer of a randomly chosen residue to another available conformer of that residue. In 50% of the cases, a multi-flip is performed if some conformers of the selected residue exhibit strong interactions with conformers in other residues. This approach allows for concerted motion or ionization to be fairly sampled.

The Monte Carlo sampling process in MCCE consists of three stages: annealing, reduction, and sampling. The annealing stage gradually lowers the temperature in the Boltzmann distribution function to room temperature, ensuring that microstate statistics are collected only at equilibrium, even if the initial microstate is far from it. The reduction stage samples microstates over a sufficient number of steps, excluding any conformers that never appear. After reduction, residues with alternative conformers are considered "free" residues. Only during the sampling stage are conformer occupancies and, optionally, microstates recorded





## Input Files:
- head3.lst 
- ms_out file
- sum_crg.out

### ms_out File Information
One of the major challenges is recording all possible millions of microstates in a readable format. The MCCE algorithm includes several approximations that are advantageous for microstate analysis. One such approximation is that conformers are premade, allowing them to be labeled for each microstate. Additionally, only a few residues change at each step, so it is only necessary to record the conformers that have changed when a microstate is accepted.

At the beginning of the file, the IDs of fixed and free conformers are saved. In the first line of each Monte Carlo run, the microstates of free conformer residues are recorded. Each subsequent line for every step includes the enthalpy (in kcal/mol) of the system, the number of times the microstate was repeated before a new state was accepted (called the count), and the IDs of the conformers of residues that are flipping.


## Script Requirements:
  - ms_analysis.py: This script loads the input file.
  - microstate_analysis.ipynb : Used for post-processing of microstates.
  - energy_calculation_ms_count.ipynb: Calculates free energy and entropy.
  - pdb_write_ms.ipynb: Writes microstates into a PDB file for visualization purposes.

  
  
  
 
