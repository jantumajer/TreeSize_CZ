# TreeSize_CZ
Data and scripts associated with the manuscript “Trend towards larger and more moisture-limited trees in Central-European temperate forests”

### Inputs
Input data involves (i) “sitef2.csv” - site characteristics of sample sites from TreeDataClim database (www.treedataclim,cz). This file is used also for matching sites with rwl files. (ii) Rwl files are attached for testing. The remaining rwl files are available upon request through TreeDataClim website. (iii) Input data also includes climatic surfaces used for extraction of climatic data for each site (precipitation – “sra_wgs_month.nc” , temperature – “t_wgs_month.nc”). For detailed description see Mašek et al. 2024 in Science of the Total Environment.

### R scripts
#### Age structure adjustment
This script was used to adjust the age structures of samples to create datasets 1990 and 2015. As inputs the sitef2.csv and rwl files are used. Script is provided in two slightly different variants used for Picea abies and Abies alba, and for the remaining species (Pinus sylvestris, Fagus sylvatica, Quercus sp.). 
## Climatic response calculation
Script reads data from climatic surfaces (t_wgs_month.nc, sra_wgs_month.nc) for each site, build tree-ring chronology, detrend SPEI time-series and calculates correlations between tree-ring chronology and SPEI for two periods before and after 1990. As inputs the sitef2.csv, rwl files and climatic surfaces are used.
## Fitting structural equations models
Script fits first linear models, test for their autocorrelation and then fits structural equations models either using linear models (autocorrelation insignificant) or spatial lag, spatial error models (autocorrelation significant). The input data are in table “pcabsem.csv”. 

### Data outputs used for fitting models and plotting figures
File “dataset-all.csv” was derived as the output of Age structure adjustment script (variables: stem diameters d90, d20, stem diameter change ddif, mean site basal area increments grate20, mean site tree age /age,age20/ number of trees /numrows20, numrows01/, percentage difference in age /agedif1/) connected with site environmental data (climatic water balance, topography wetness index, soil chemistry variables and their principal components) and site chronology correlations with SPEI (corS20, corS90, difference in correlations cordif). This file was used to draw Figure 2 and 4. After subsetting and repeated derivation of soil principal components, dataset was used to fit piecewise SEM models (example file for Picea abies is “pcabsem.csv”).
File “coreltable.csv” represents an output from the Climatic response calculation script. This file was used as a source of correlation coefficients between growth and SPEI.
