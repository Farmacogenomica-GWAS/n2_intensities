# n2_intensities File Processing

This document describes the processing of the `n2_intensities.hdf5` file using Python and the `h5py` and `pandas` libraries. The primary goal was to extract relevant data from the file and convert it into a more accessible CSV format. The `n2_intensities.hdf5` file was obtained by using the Tierpsy Tracker and contains information related to worm intensities.

**Key Steps:**

1.  **File Inspection:** The `n2_intensities.hdf5` file was inspected to identify its top-level datasets and groups. The sizes of the top-level datasets were printed to the console.

2.  **Top-Level Dataset Extraction:** The following top-level datasets were extracted and converted to individual CSV files:
    * `straighten_worm_intensity_median`
    * `trajectories_data_valid`

3.  **Group Data Extraction:**
    * **`provenance_tracking` Group:** The attributes (`CLASS`, `TITLE`, `VERSION`) within the `provenance_tracking` group were extracted and saved as a single-row CSV file.

4.  **Output Format:**
    * Top-level datasets were saved as individual CSV files with column headers derived from the dataset structure.
    * The attributes from the `provenance_tracking` group were saved as column headers in a single-row CSV file named `provenance_tracking.csv`.

5.  **Visualization of the datasets:** The first 5 rows of each generated CSV file (from both top-level datasets and the `provenance_tracking` group) were printed to the console to provide a quick overview of the extracted data.

**Libraries Used:**

* `h5py`: For reading and navigating the HDF5 file structure, accessing datasets and groups, and reading attributes.
* `pandas`: For creating and exporting DataFrames to CSV files and for displaying the first few rows.
* `numpy`: Used implicitly by `h5py` for handling array data.
* `os`: For handling file paths and directory creation.

**Purpose:**

The processing steps outlined here were performed to make the intensity-related data contained within the `n2_intensities.hdf5` file more readily available for analysis. The conversion to CSV format allows for easier manipulation and exploration of the data using standard data analysis tools. The extraction of metadata from the `provenance_tracking` group was handled separately to capture this information. Visualizing the first few rows of each output CSV provides a quick check of the extraction process.
