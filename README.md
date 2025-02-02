[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.10075553.svg)](https://doi.org/10.5281/zenodo.10075553)

Tensor network approximate contractions for optimization (tnac4o)
============
Accompanying article:
M. M. Rams, M. Mohseni, D. Eppens, K. Jałowiecki and B. Gardas, 
"Approximate optimization, sampling and spin-glass droplets discovery with tensor networks", [Phys. Rev. E 104, 025308 (2021)](https://doi.org/10.1103/PhysRevE.104.025308), [arXiv:1811.06518](https://arxiv.org/abs/1811.06518)

Documentation: https://tnac4o.readthedocs.io/en/latest/

**tnac4o** is an open-source package to heuristically solve Ising-type optimization problems defined on quasi-2d lattices, including, for instance, the chimera graph.
It employs tensor network contractions to calculate marginal probabilities and identify the most probable states from Gibbs distribution.
By identifying spin-glass droplets, it allows one to reconstruct the low-energy spectrum of the model.
It can also be used for Random Markov Fields defined on a 2d lattice.

Installation
------------
In the main folder run:
   ```
   pip install .
   ```
Make sure you are using python 3.6 or newer. 

Usage examples
--------------

See folder [examples](examples) for a set of scripts showing basic applications of the package.
Most of the examples concern with Ising problems defined on a chimera graph. We include a set of hard _droplet instances_ defined on chimera graphs of sizes _L_=128,512,1152,2048, see folder [instances](instances). 

For example, to find the ground state of instance number 1 for _L_=128 run:
   ```
   python e01_search_gs_droplet_instances.py -L 128 -ins 1
   ```
To see some of the other available options run:
   ```
   python e01_search_gs_droplet_instances.py -h
   ```
See the documentation for further details.

Other examples include:

Sampling from a Gibbs distribution, here at inverse temperature _beta_=1
   ```
   python e02_sample_droplet_instances.py -L 128 -ins 1 -b 1
   ```
   
Searching for a structure of low-energy excitations and saving the result to a file (in folder [examples/results](examples/results))
   ```
   python e03_search_spectrum_droplet_instances.py -L 128 -ins 1 -s
   ```

Loading the solution from the previous script, and reconstructing the low-energy states:
   ```
   python e04_load_spectrum_droplet_instances.py -L 128 -ins 1
   ```

A minimal example of a problem defined as a Random Markov Field see:
   ```
   python e05_minimal_RMF.py
   ```

Script counting ground state degeneracy for a class of discrete instances in the paper (Fig. 4):
   ```
   python e06_search_gs_degeneracy_J124.py
   ```

