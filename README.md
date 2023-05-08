# amylase-reaction-discovery

# How and When Does an Enzyme React? Unraveling α-Amylase Catalytic Activity with Enhanced Sampling Techniques

# Sudip Das, Umberto Raucci, Rui P. P. Neves, Maria J. Ramos, Michele Parrinello 

# https://doi.org/10.26434/chemrxiv-2023-h1498


This archive contains all the input files needed to reproduce the results of the paper.


In the 'classical_unbiased_MD' folder the following files are available:
- All the initial conformations.
- A folder name 'template' containing all the GROMACS inputs for classical energy minimization, MD equilibration and production runs.
- A folder named 'unbiasedCVs' containing PLUMED input and coordinate alignment file. This are required to produce Figure 4b.


In the 'QM-MM_MD' folder the following files are available:
- Discovery simulations separately with two different graph CVs:
  * 8 atoms within the adjacency matrix (8atomsCV) and 34 atoms within the adjacency matrix (34atomsCV)
- Each of these two folders have subfolders containing inputs for running discovery simulations from each intial conforamtions.
  * MD_nvt_prod_frameID_amber.xyz is the initial conformation (IC).
  * amylase_ee.prmtop, forceeval_qmmm.cp2k-frameID.inc and react_nvt-ee_gpw_opes_new.inp are CP2K input files.
  * plumed.dat is the PLUMED input, num_cv.pt file contains the spectral graph CV.
  * label.dat mentions all the atoms included within the adjacency matrix.
  * make_plumed_qm_mm.py is a python script to produce the plumed.dat file.


The 'Wannier_centers' folder contains input files for the calculation of Wannier centers.


In the 'classical_biased_MD' folder the following files are available:
- glycam_06h.itp, amylase_GMX.top, index.ndx, nvt_prod.mdp are the GROMACS input.
- Folders 0, 1, 2, 3 contain starting coordinate file for the corresponding replica.
- plumed.dat is the PLUMED input, npt_eqm3_align2z_CA.pdb is a coordinate alignment file and the *.pt files contain the Deep-TDA neural network model Contact and Water CVs.
- init_path.pdb and final_path.pdb are the initial guess path and final path, respectively, for the path CV.



More information about using PLUMED with Pytorch can be found at https://github.com/luigibonati/data-driven-CVs.
More information about OPES can be found at https://github.com/invemichele/opes.
More information about spectral graph CV can be found at https://github.com/uraucci/discovery_CVs.
More information about the calculation of high water density spots and their centers can be found at https://github.com/narjesansari/Hydration_spot.git.
More information about Deep TDA CV can be found at https://colab.research.google.com/drive/1TO7bAkmIznsdfea2i5NXfNtytJrnkkIt?usp=sharing.

The simulations were performed with GROMACS 2021.5, CP2K 9.1, PLUMED 2.9 and Pytorch 1.8. 



If you have comments or questions please send an email to das.sudip37@gmail.com
