# Florida Ocean

This project is my final project for the class CS185C.

## Science Question: How does increased humidity in in Florida's coast affect the ocean temperature?

# Project Description
  In this project I wanted to investigate the effects increased humidity had on the temperature of the ocean, specifically in Florida. In 2004, Florida towards the end of the year had a pretty intense hurricane season. One of the factors contributing to hurricanes is humidity, so I wanted to test if increasing the humidity had an effect on the ocean temperature. My hypothesis was that the humidity would make the hurricane's effects on temperature worse as the ocean velocity would maybe increase, increasing the temperature of the ocean around the coast of Florida.

  To test my hypothesis, my model will focus on just a small window including Florida's coast. I will run my experiment for the whole year of 2004 and see if the ocean temperature had any intense changes if I run the model once with normal humidity, and another time if I increased the humidity by 50%. I will use the ECCO Version 5 model in 2004 for my initial data and to ultimately analyze my results, I will create movies highlighting the tempterature of the ocean– one with increased humidity and one without.
  
# Reproducing Model Results
## Step 1: Create the Model Files
  Generate the following list of files using the notebooks indicated in parentheses:
  * Model Grid (notebooks/Creating the Model Grid.ipynb)
  * Bathymetry (notebooks/Creating the Bathymetry.ipynb)
  * Initial Conditions (notebooks/Creating the Initial Conditions.ipynb)
  * External Forcing Conditions (notebooks/Creating the External Forcing Conditions.ipynb)
  * Boundary Conditions (notebooks/Creating the Boundary Conditions.ipynb) The model files should be placed into the input directory.

## Step 2: Add files to the computing cluster
  These files can be now put in your scratch directory onto the computing cluster. First make sure to clone MITgcm on ur directory, make a configurations folder, and then a folder for your project and your code, namelist, run, and input. Use the scp command to transfer your input data since the file sizes are large.
  Like so: mkdir MITgcm/configurations/FloridaOcean
  
## Step 3: Compile the model
  Make a build directory as well in the FloridaOcean folder and make sure to run the following lines: ../../../tools/genmake2 -of ../../../tools/build_options/darwin_amd64_gfortran -mods ../code -mpi
make depend
make

Make sure that you redo this step every time you need to edit the SIZE.h file as well.

## Step 4: Run the model
  Link everything from input and code to yhe run directory. When running the model, make sure your data.exf file has all the right information. When you run the model the first time, run it with the normal AQH_2004 data as well as setting the interpolation to 0. The second time, use your AQH_MODIFIED_2004 data and set interpolation to 1.5 to indicate an increase in humidity. Submit the job script twice. 
  And if you encounter a specific error where you need files with and extra 2004 at the end for some reason, make sure to copy all the data.exf files to duplicate files with an extra 2004 at the end too. But if not proceed as normal with your original files.
  Another note, make sure to double check all the spaces are consistent in your data."" files and that all the lines are aligned to prevent future errors.
  
## Step 5: Analyze the results
  Use the two notebooks for analysis. 
  1. Analyzing Model Results - This is to look at the spacial and temporl variations in the temperature field in the model with increased humidity. It also generates a visualization provided in the figures directory.
  2. Answering Science Question - This provides analysis to the plot and addresses the science question posed at the beginning of the project.
