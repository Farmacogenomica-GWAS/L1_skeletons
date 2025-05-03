# L1_featuresN File Processing

This document describes the processing of the `L1_featuresN.hdf5` file using Python and the `h5py` and `pandas` libraries. The primary goal was to extract relevant data from the file and convert it into a more accessible CSV format. The `L1_featuresN.hdf5` file was obtained by using the Tierpsy Tracker.

**Key Steps:**

1.  **File Inspection:** The `L1_featuresN.hdf5` file was inspected to identify its structure and contents. This involved examining the groups and datasets within the file.
2.  **Dataset Extraction:**
    * The following datasets were extracted and converted to individual CSV files:
        * `blob_features`
        * `features_stats`
        * `timeseries_data`
        * `trajectories_data`
    * The data within the `coordinates` group was extracted and converted to a CSV file.  This involved reshaping the 3D arrays within the group (specifically, 'dorsal_contours', 'skeletons', and 'ventral_contours') to a 2D format for compatibility with CSV.
    * The attributes within the `provenance_tracking` group were extracted and converted to a single-row CSV file.

3.  **Output Format:** All extracted data was saved as CSV files, with column headers derived from the dataset structure (where applicable).  For the 'coordinates' group, the reshaped data was saved with new column names (e.g., `dorsal_contours_0`, `dorsal_contours_1`, etc.).  For the 'provenance_tracking' group, the attributes were saved as column headers in a single-row CSV.

**Libraries Used:**

* `h5py`: For reading and navigating the HDF5 file structure.
* `pandas`: For creating and exporting DataFrames to CSV files.
* `numpy`: For reshaping arrays during the extraction of the 'coordinates' group.

**Purpose:**

The processing steps outlined here were performed to make the data contained within the `L1_featuresN.hdf5` file more readily available for analysis. The conversion to CSV format allows for easier manipulation and exploration of the data using standard data analysis tools.  The reshaping of the 'coordinates' data and the extraction of 'provenance_tracking' attributes were necessary to handle the specific structure of this HDF5 file.
