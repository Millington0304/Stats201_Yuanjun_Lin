The data file is of excessively large size to upload, it can be accessed with an installed curl command with running the Windows batch scripts.
Copy and modify the command to run on MacOS or Linux.

In these files, monthly maximum, minimum and mean temperature (deg. C. to 100ths) and precipitation (mm to 100ths) are computed for each month from 1895-present. The latest month is appended to these period of record
NetCDF files and are based on the GHCN dataset using a 5km gridded approach. 
The actual grid is 1/24th of a degree. The 1385x596 grid covers CONUS but the non-land points are filled with NaN.In these files, monthly maximum, minimum and mean temperature (deg. C. to 100ths) and precipitation (mm to 100ths) are computed for each month from 1895-present. The latest month is appended to these period of record
NetCDF files and are based on the GHCN dataset using a 5km gridded approach. 
The actual grid is 1/24th of a degree. The 1385x596 grid covers CONUS but the non-land points are filled with NaN.

**Dataset Descriptor: CONUS Climate Grid Data (1895-Present)**

1. **Overview:**
   - **Title:** Continental United States (CONUS) Climate Grid Data
   - **Temporal Coverage:** 1895-Present
   - **Spatial Coverage:** Continental United States (CONUS)
   - **Spatial Resolution:** 1/24th of a degree grid (Approximately 5km at equator)
   - **Grid Dimensions/Resolution:** 1385 x 596

2. **Data Structure:**
   - **Format:** NetCDF
   - **Data Source:** Global Historical Climatology Network (GHCN, NOAA)
   - **Gridding Approach:** 5km gridded data based on GHCN dataset

3. **Variables:**
   - **Column 1:** Latitude (in decimals rather than degrees)
   - **Column 2:** Longitude (in decimals rather than degrees)
   - **Column 3:** Precipitation (mm to 100ths)
   - **Columns 4-15:** Monthly Climate Data
     - Includes maximum, minimum, and mean temperature (degrees Celsius to 100ths) and precipitation (mm to 100ths) for each month

4. **Data Processing:**
   - **Computation Method:** Monthly values are computed for each grid point
   - **Data Append Strategy:** The latest month's data is appended to the period of record in the NetCDF files

5. **Quality and Reliability:**
   - **Data Filling:** Non-land grid points (such as water bodies) are filled with NaN (Not a Number) to indicate no data
   - **Data Accuracy:** Reflects the accuracy and limitations of the GHCN dataset and the gridding methodology

6. **Usage Notes:**
   - **Intended Use:** This dataset is suitable for climate analysis, research on climate variability and change, and related applications over the CONUS region.
   - **User Responsibility:** Users should be aware of the spatial resolution and the limitations in terms of non-land data points.

7. **References:**
   - **GHCN Dataset:** Provides the foundational data for this gridded approach.
   - **NetCDF Format:** An industry-standard for array-oriented scientific data.

8. **Update Frequency:**
   - **Data Updates:** The dataset is updated monthly with the inclusion of the latest month's data.

This descriptor provides a comprehensive overview of the CONUS Climate Grid Data, including its structure, variables, and usage considerations.
