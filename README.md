# Cut-based Conflict Analysis in Mixed Integer Programming

This archive is distributed in association with the INFORMS Journal on Computing under the Apache 2.0 License.

The software and data in this repository are snapshots used in the research reported in the paper Cut-based Conflict Analysis in Mixed Integer Programming by Gioni Mexi, Felipe Serrano, Timo Berthold, Ambros Gleixner, Jakob Nordström.

## Cite
- **Paper**: Gioni Mexi, Felipe Serrano, Timo Berthold, Ambros Gleixner, Jakob Nordström.  
  "Cut-based Conflict Analysis in Mixed Integer Programming."  
  TBD https://doi.org/INSERT_DOI

- **Software**:

  ```bibtex
  @article{bolusani2024scip,
    title={The SCIP optimization suite 9.0},
    author={Suresh Bolusani and Mathieu Besançon and Ksenia Bestuzheva and Antonia Chmiela and João Dionísio and Tim Donkiewicz and Jasper van Doornmalen and Leon Eifler and Mohammed Ghannam and Ambros Gleixner and Christoph Graczyk and Katrin Halbig and Ivo Hedtke and Alexander Hoen and Christopher Hojny and Rolf van der Hulst and Dominik Kamp and Thorsten Koch and Kevin Kofler and Jurgen Lentz and Julian Manns and Gioni Mexi and Erik Mühmer and Marc E. Pfetsch and Franziska Schlösser and Felipe Serrano and Yuji Shinano and Mark Turner and Stefan Vigerske and Dieter Weninger and Liding Xu},
    journal={arXiv preprint arXiv:2402.17702},
    year={2024}
  }
  ```

## Compilation

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

## Settings
We tested three SCIP setting files in our experiments:
- `settings/default.set`
- `settings/mir-conflicts.set`
- `settings/coeftight-conflicts.set`

## Test set
Evaluated on a subset of MIPLIB instances.  
See `data/testset.test` for the instance list; raw `.mps.gz` files are in `data/instances/`.

## Running experiments
To solve an instance use:
```bash
path/to/bin/scip -s settings/mir-conflicts.set -f data/instances/<instance-name>.mps.gz
```

## Results
Aggregated and raw results are in the `results/` directory.
