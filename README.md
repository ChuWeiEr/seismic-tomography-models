# seismic-tomography-models

In this database, I collected several whole mantle tomography results, and
converted them into nc files. Each nc files contain 4 variables: depth,
longitude, latitude and "v". The "v"alues could represent either S or P wave
speed (in km/s), velocity purturbation (%), density (in kg/m^3), Q or
anisotropic parameters, etc. The details(comments) are within each nc files,
but the file name roughly indicate which value it represent.

Most of the model are downloaded from IRIS SPUD Service:\
http://ds.iris.edu/spud/earthmodel\
Others are downloaded from links in papers or from authors' websites and etc.

The c++ tool to read and linear interpolate between values are provided in this file:\
https://github.com/shuleyu/CPP-Library/blob/master/Tomography.hpp  
Example program is:\
https://github.com/shuleyu/CPP-Library/blob/master/Examples/Tomography.cpp

Here are details about download sources and convertions to these nc files:

1. GyPSum_vs.nc\
Paper        : doi:10.1029/2010JB007631\
Download link: http://ds.iris.edu/spud/earthmodel/10131119 (netCDF binary of S velocity expressed as km/s)\
Changes      : rename variable "vs" to "v".

2. GyPSum_vp.nc\
Paper        : doi:10.1029/2010JB007631\
Download link: http://ds.iris.edu/spud/earthmodel/10131119 (netCDF binary of P velocity expressed as km/s)\
Changes      : rename variable "vp" to "v".

3. SEMum_vs.nc\
Paper        : doi:10.1111/j.1365-246X.2011.04969.x\
Download link: http://ds.iris.edu/spud/earthmodel/10131263 (the netCDF binary for the above model expressed as absolute velocity)\
Changes      : lose variable "xi", rename variable "vs" to "v".

4. SEMum_xi.nc\
Paper        : doi:10.1111/j.1365-246X.2011.04969.x\
Download link: http://ds.iris.edu/spud/earthmodel/10131263 (the netCDF binary for the above model expressed as absolute velocity)\
Changes      : lose variable "vs", rename variable "xi" to "v".

5. MITP08_dvp.nc\
Paper        : doi:10.1029/2007GC001806
Download link: https://agupubs.onlinelibrary.wiley.com/action/downloadSupplement?doi=10.1029%2F2007GC001806&file=ggge1202-sup-0002-ds01.txt.gz\
Changes      : convert the ascii file into nc file. rename variable "dvp" to "v".

6. MITP08_vp.nc\
Paper        : doi:10.1029/2007GC001806
Download link: https://agupubs.onlinelibrary.wiley.com/action/downloadSupplement?doi=10.1029%2F2007GC001806&file=ggge1202-sup-0002-ds01.txt.gz\
Changes      : convert dvp into vp using ak135 reference model and create this nc file in which "v" representing "vp".
