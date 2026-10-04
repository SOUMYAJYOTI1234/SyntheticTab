# Data

This directory holds datasets locally. It is not used to version data.

- `raw/`: original, unmodified datasets as obtained from their source. **Raw data must not be committed to Git.**
- `processed/`: cleaned and transformed datasets produced by the project's preprocessing code. **Processed data should generally not be committed either**, unless a specific decision is made to do so.

Both folders are excluded in `.gitignore`. Only the `.gitkeep` placeholders are tracked.

## Dataset documentation

No dataset has been selected yet. Once datasets are chosen, this file will record for each one:

- source and how to obtain it
- license and terms of use
- version or download date
- preprocessing decisions (e.g. handling of missing values, encoding of categorical variables, train/test splits)
