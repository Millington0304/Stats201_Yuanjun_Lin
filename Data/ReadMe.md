**CONUS Climate Grid Data (1895-Present)**
This dataset is chosen for its reliability and completeness due to the nature of being sourced from NOAA by the US government. The data is obtained by NOAA through industry-standard meteorological measurement instruments.
Flowchart for intuitive access available at: https://whimsical.com/dataset-flow-12AtVsN89yL3mAMszdqwnK

1. **Overview:**
   - **Title:** Continental United States (CONUS) Climate Grid Data (on temperature and precipitation)
   - **Temporal Coverage:** 1895-Present
   - **Spatial Coverage:** Continental United States (CONUS)
   - **Spatial Resolution:** 1/24th of a degree grid (Approximately 5km at the equator)
   - **Grid Dimensions/Resolution:** 1385 x 596

2. **Data Structure:**
   - **Format:** NetCDF
   - **Data Source:** Global Historical Climatology Network (GHCN, NOAA)
   - **Gridding Approach:** 5km gridded data based on GHCN dataset

3. **Dictionary of Variables:**
   - **Column 1:** Latitude (in decimals)
   - **Column 2:** Longitude (in decimals)
   - **Column 3:** Precipitation (mm to 100ths)
   - **Columns 4-15:** Monthly Climate Data (Jan-Dec)
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

7. **Formats**
   - **GHCN Dataset:** Provides the foundational data for this gridded approach. (Tentatively adopted for better versatility)
   - **NetCDF Format:** An industry standard for array-oriented scientific data.

8. **Update Frequency:**
   - **Data Updates:** The dataset is updated monthly with the inclusion of the latest month's data.
9. **Reference:**
   - National Oceanic and Atmospheric Administration (NOAA). (n.d.). Gridded Climate Datasets. National Centers for Environmental Information. Retrieved at Jan 24th 2024, from https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.ncdc%3AC00332
