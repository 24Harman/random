# PRISM: Risk Factor Model

## Setting Up the Workspace

1. **Copy Necessary Files**:

   - Navigate to the `runner` folder.
   - Copy `env.py` and the sample configuration file (`sample_cfg`) to your PRISM workspace.

2. **Modify the Configuration**:

   - Edit the configuration file (`cfg`) to suit your specific requirements.

## Constructing Risk Factors

1. Create a risk factor file in the format provided in `sample_risk/risk.py`.

## Generating Risk Factors

1. Open an IPython shell.

2. Import the `env` module:

   ```python
   import env
   ```

3. Initialize the Risk Factor Generator:

   ```python
   rfg = env.init(book_name, risk_dir, cfg_fpath)
   ```

   - `book_name`: This value is specified in the configuration file (`cfg`).
   - `risk_dir`: Directory containing your `risk.py` file.
   - `cfg_fpath`: Path to the modified configuration file.

4. Generate Risk Factors:

   ```python
   rfg.generate(univ_name)
   ```

   - `univ_name`: Specify the universe, e.g., `'FULL'` / `'IN_TOP_120'`.... .

## Visualizing and Transforming Factors

- After generating the risk factors, a Jupyter notebook will be copied to your workspace.
- Use this notebook to:
  - Visualize factor characteristics.
  - Perform customisations on risk dataframe and visualise the transformation effects.
- Make final changes to risk.py and regenerate (if required).

## Saving Outputs

1. Save All Outputs:

   ```python
   rfg.save_outputs(overwrite=False)
   ```

   - Use the `overwrite` parameter to specify whether to overwrite existing files.

2. Save Outputs Individually:

   - Save z-scores:
     ```python
     rfg.save_zscore(overwrite=False)
     ```
   - Save ranked HDF5:
     ```python
     rfg.save_ranked_hdf5(overwrite=False)
     ```
   - Save idea files:
     ```python
     rfg.save_idea(overwrite=False)
     ```
   - Save style HDF5:
     ```python
     rfg.save_style_hdf5(overwrite=False)
     ```
