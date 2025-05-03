# L1_skeletons File Processing

This document describes the processing of the `L1_skeletons.hdf5` file using Python and the `h5py`, `pandas`, and `numpy` libraries. The primary goal was to extract relevant data from the file and convert it into a more accessible CSV format. The `L1_skeletons.hdf5` file was obtained by using the Tierpsy Tracker.

**Key Steps:**

1.  **File Inspection:** The `L1_skeletons.hdf5` file was inspected to identify its structure and contents. This involved examining the groups and datasets within the file.
2.  **Dataset Extraction:**
    * The following datasets were extracted and converted to individual CSV files:
        * `blob_features`
        * `contour_area`
        * `contour_side1`
        * `contour_side1_length`
        * `contour_side2`
        * `contour_side2_length`
        * `contour_width`
        * `plate_worms`
        * `skeleton`
        * `skeleton_length`
        * `trajectories_data`
        * `width_midbody`
    * For the `contour_side1`, `contour_side2`, and `skeleton` datasets, which were originally 3D arrays, the data was reshaped into a 2D format to ensure compatibility with the CSV format.

3.  **Output Format:** All extracted data was saved as CSV files, with column headers derived from the dataset structure.  For the `contour_side1`, `contour_side2`, and `skeleton` datasets, the reshaped data was saved with new column names to reflect the new 2D structure.

**Libraries Used:**

* `h5py`: For reading and navigating the HDF5 file structure.
* `pandas`: For creating and exporting DataFrames to CSV files.
* `numpy`: For reshaping arrays during the extraction of the `contour_side1`, `contour_side2`, and `skeleton` datasets.

**Purpose:**

The processing steps outlined here were performed to make the data contained within the `L1_skeletons.hdf5` file more readily available for analysis. The conversion to CSV format allows for easier manipulation and exploration of the data using standard data analysis tools.  The reshaping of the `contour_side1`, `contour_side2`, and `skeleton` datasets was necessary to handle their original 3D structure and make them suitable for CSV export.
