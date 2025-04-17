# Craton-deposits_Tectonic-evolution
How Subduction Evolution and Tectonic Stability Drive Sediment-Hosted Mineralization Along Craton Edges

[![DOI](https://zenodo.org/badge/947658549.svg)](https://doi.org/10.5281/zenodo.15015718)

![Alt text](/https://github.com/EarthByte/Craton-deposits_Tectonic-evolution/Sample_Layouts.JPG](https://github.com/EarthByte/Craton-deposits_Tectonic-evolution/blob/main/Sample_Layouts.JPG)

# Step 1:
Notebook_1: 01_CalculateSpatialRelationships.ipynp

  Calculate Spatial Relationships 
  
  Split polylines into segments based on azimuth changes.
  It also calculates other spatial values between two lines (e.g., rift datasets and craton boundaries or points), but these are not used at this stage in this project.  
  
  Inputs: Craton_Line.shp, Deposit_Point.shp  
  Outputs: merged_segmented_craton.shp (line 2), and Deposits_SpatialRelationships.shp  

# Step 2:
Notebook_2: 02_Segmented_Craton_v3.ipynp

  Framework for Interrogating Craton Boundary Segments, Deposits, and Plate Tectonic Parameters Over Time (1800 Ma) Using Mantle Frame Rotation Files
   
  This notebook enables users to extract plate tectonic features on a global scale. It consists of three main sections.
  In the first section, we extract features at the exact formation time of deposit datasets, followed by the preparation and visualization of histograms and rose diagrams considering the number of deposits and total metal content.
  The second section involves extracting features for a median or mean of a (e.g. 10 million years here) a-million-year period prior to the formation of deposits. This approach helps smooth out any potential spikes in model uncertainty associated with the ages of deposits and the models themselves.
  The third section focuses on extracting the gradient of features from g (10 here) to zero million years before the formation of deposits.
  The diagrams represent two key aspects: the first shows the number of deposits, while the second illustrates the weighted distribution based on total metal content.  

  Inputs: 1.8Ga_model_optimised_mantle_ref_frame, Deposits_SpatialRelationships.shp, merged_segmented_craton.shp  
  Outputs: segmented_craton_features.shp

# Step 3:
Notebook_3: 03_Subduction_Segment_Length.ipynb

  Calculating Length of Subduction Segments.  
  
  Inputs: 1.8Ga_model_optimised_mantle_ref_frame, Deposits_SpatialRelationships.shp, merged_segmented_craton.shp  
  Outputs: segmented_craton_features.shp (with columns sub_len, and sub_len_m)

# Step 4:
Notebook: Generating_Random_Points.ipynp
  Function to generate random points uniformly within a polygon.  
  
  Input: Buffer185km.shp  
  Output: random_points_with_ages.shp

# Step 5:
"We apply Step 1, Step 2, and Step 3 to the random points in order to extract the same features, replacing 'Deposit_Point.shp' with 'random_points_with_ages.shp'."

# Step 6: 
Merge the attribute columns of Deposit_Point.shp and random_points_with_ages.shp to enable comparison between deposit and random points.  

Output: deposits_VS_random.csv

# Step 7: 
Notebook: Plots.ipynb  

  Input: deposits_VS_random.csv  
  Output: 
    Bar charts
    Scatter plots
    3D scatter plots
    Cumulative Distribution Functions (CDFs)
    Violin box plots

# Step Creating Movie:  

Notebook: Creating_Movie.ipynb
Movie from 1800 Ma to the present with 1 Ma year interval  

Inputs: 1.8Ga_model_optimised_mantle_ref_frame, Craton_Line.shp, Deposit_Point.shp 
Outputs: 1800 png files, Movie.mp4









