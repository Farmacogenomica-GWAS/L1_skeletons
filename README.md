# L1_skeletons File Processing

This document describes the processing of the `L1_skeletons.hdf5` file using Python and the `h5py` and `pandas` libraries. The primary goal was to extract relevant data from the file and convert it into a more accessible CSV format. The `L1_skeletons.hdf5` file was obtained by using the Tierpsy Tracker.

**Key Steps:**

1.  **File Inspection:** The `L1_skeletons.hdf5` file was inspected to identify its structure and contents. This involved examining the groups and datasets within the file.
2.  **Dataset Extraction:**
    * The following top-level datasets were extracted and converted to individual CSV files:
        * `blob_features`
        * `contour_area`
        * `contour_side1` (reshaped to 2D)
        * `contour_side1_length`
        * `contour_side2` (reshaped to 2D)
        * `contour_side2_length`
        * `contour_width`
        * `plate_worms`
        * `skeleton` (reshaped to 2D)
        * `skeleton_length`
        * `trajectories_data`
        * `width_midbody`
    * Datasets within groups were also extracted:
        * `intensity_analysis/switched_head_tail`
        * `timestamp/raw`
        * `timestamp/time`
    * Scalar datasets within the `provenance_tracking` group were extracted into a single CSV file.

3.  **Output Format:** All extracted data was saved as CSV files. For datasets that were originally multi-dimensional (e.g., `contour_side1`, `contour_side2`, `skeleton`), the data was reshaped into a 2D format before saving. Datasets extracted from groups had their filenames adapted to reflect their group structure (e.g., `intensity_analysis_switched_head_tail.csv`). Scalar data from `provenance_tracking` was saved in a `provenance_tracking_scalars.csv` file with 'name' and 'value' columns.

4.  **Visualization of the datasets:** The first 5 rows of the CSV files generated from the top-level datasets were printed to the console under the category "Top-Level Datasets". Similarly, the first 5 rows of the CSV files generated from datasets within groups were printed under the category "Datasets Extracted from Groups", providing a quick overview of the extracted data.

**Libraries Used:**

* `h5py`: For reading and navigating the HDF5 file structure, including accessing datasets within groups and scalar data.
* `pandas`: For creating and exporting DataFrames to CSV files and for displaying the first few rows.
* `numpy`: For reshaping multi-dimensional arrays (like `contour_side1`, `contour_side2`, and `skeleton`) into a 2D format suitable for CSV.

**Purpose:**

The processing steps outlined here were performed to make the data contained within the `L1_skeletons.hdf5` file more readily available for analysis. The conversion to CSV format allows for easier manipulation and exploration of the data using standard data analysis tools. The script handles both top-level datasets and those nested within groups, as well as scalar metadata, providing a comprehensive extraction of the file's contents. Finally, visualizing the first few rows of each output CSV helps in quickly understanding the structure and content of the extracted data.

