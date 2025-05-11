[![INFORMS Journal on Computing Logo](https://INFORMSJoC.github.io/logos/INFORMS_Journal_on_Computing_Header.jpg)](https://pubsonline.informs.org/journal/ijoc)

# Cut-based Conflict Analysis in Mixed Integer Programming

This archive is distributed in association with the INFORMS Journal on Computing under the Apache 2.0 License.

The software and data in this repository are snapshots used in the research reported in the paper Cut-based Conflict Analysis in Mixed Integer Programming by Gioni Mexi, Felipe Serrano, Timo Berthold, Ambros Gleixner, Jakob Nordström.

## Cite
To cite the contents of this repository, please cite both the paper and this repo, using their respective DOIs.

https://doi.org/10.1287/ijoc.2024.0999

https://doi.org/10.1287/ijoc.2024.0999.cd

Below is the BibTex for citing this snapshot of the repository.

```
@misc{Mexi2024,
  author =        {G. Mexi, F. Serrano, T. Berthold, A. Gleixner, J. Nordström},
  publisher =     {INFORMS Journal on Computing},
  title =         {{Cut-based Conflict Analysis in Mixed Integer Programming}},
  year =          {2024},
  doi =           {10.1287/ijoc.2024.0999.cd},
  url =           {https://github.com/INFORMSJoC/2024.0999},
  note =          {Available for download at https://github.com/INFORMSJoC/2024.0999},
}  
```

## Description
This repository provides the data and implementation accompanying the paper:
Cut-based Conflict Analysis in Mixed Integer Programming

All algorithms are implemented in SCIP (https://www.scipopt.org/) and will be included in the next SCIP release.

The new conflict analysis algorithms are implemented in:
- `src/scip/src/scip/conflict_resolution.c`

We evaluated three different parameter settings in our experiments:
- `settings/default.set`
- `settings/mir-conflicts.set`
- `settings/coeftight-conflicts.set`

## Building

- **papilo** (commit `957a9668`):
  ```bash
  git clone https://github.com/scipopt/papilo.git
  cd papilo && git checkout 957a9668
  mkdir build && cd build
  cmake .. && make -j
  ```

- **soplex** (commit `07c65b25`):
  ```bash
  git clone https://github.com/scipopt/soplex.git
  cd soplex && git checkout 07c65b25
  mkdir build && cd build
  cmake .. && make -j
  ```
- **SCIP**: follow instructions in `src/scip/INSTALL.md`

## Test set
Evaluated on a subset of MIPLIB 2017 instances. See `data/testset.test` for the instance list; raw `.mps.gz` can be downloaded from  https://miplib.zib.de/.

## Running experiments
To solve an instance use:
```bash
path/to/bin/scip -s settings/mir-conflicts.set -f path/to/instance-name.mps.gz
```

## Results
Aggregated and raw results are in the `results/` directory.
