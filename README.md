# Galaxy Tool wrappers

This repo is part of my bachelor's project "Adapting Computational Tools for Microbial Evolution and Host-Association Analysis in [Galaxy](https://github.com/galaxyproject/galaxy)".
It is a work in progress and I will add wrappers for tools and commands while I work on them.

Other repositories with Galaxy tools:

 * [IUC repo](https://github.com/galaxyproject/tools-iuc)
 * [Björn Grüning repo](https://github.com/bgruening/galaxytools)

## PhyloPhlAn 3

https://github.com/biobakery/phylophlan

PhyloPhlAn is an integrated pipeline for large-scale phylogenetic profiling of genomes and metagenomes.

### Galaxy Tools

- PhyloPhlAn (phylophlan and phylophlan_write_config_file) - **Almost ready**

  The main PhyloPhlan script for running the Supermatrix and Supertree pipelines.  
  The wrapper combines the configuration and analysis steps into one tool.
  
  Note that the current Galaxy wrapper imposes some limitations on how the tool can be used:
  - Support for the external tools *Opal*, *UPP* and *astrid* is missing at the moment, as well as the ability to add custom tools.
  - Using aligned markers from StrainPhlAn (--strainphlan) is not supported.
  - Some special options for working with the included databases are not yet implemented.
  - Input fasta files must either have the extensions '.fna' or '.faa' in the galaxy history in order for the tool to detect them.

- Assign SGBs (phylophlan_assign_sgbs) - **Stalled**
  
  This script reports the closest species-level genome bins, for each bin from a metagenomic assembly analysis.  
  The wrapper is mostly finished, but I am missing testing data for the submission. It also does not do anything without a data manager to provide the SGB database.

- Visualize metagenomic SGBs (phylophlan_draw_metagenomic) - **Almost Ready**
  
  Used to visualize the results from phylophlan_assign_sgbs. It is finished, but not useful on its own.

- phylophlan_strain_finder - **Not started**
  
  Used to perform analysis on trees built with phylophlan.

### Notes for Galaxy administrators

To be able to use the marker databases and SGBs provided with PhyloPhlAn, 
or to download reference genomes for specific species and core taxonomic proteins,
the administrator of your Galaxy instance should also install the data managers associated with this tool suite.

A PhyloPhlAn analysis can take a long time and requires quite a bit of computational recources.

## FastSpar (WIP)

https://github.com/scwatts/fastspar

FastSpar is a tool for rapid and scalable correlation estimation for compositional data.
