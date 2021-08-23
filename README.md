# CYSD_Intern

### In[28]

here I am simply exploring the HARCI-EU data and getting familiar with tiff data and Python libraries to work with.

### In[32]

``ren_ene_map.tif`` is a generated GeoTiff file from the HARCI-EU Data that takes into matter renewable energy plants, data is clipped around Paris, France. This choice follows available economic data provided by the HARCI-EU paper (as is seen in ``In [41]``).
``ren_ene_map.tif`` is composed of 4 bands. 1st band contains the plants locations and 4th band is the outline of the map ( ``Output [34]``) , second and 3rd band are just copies of the 1st one.
The Classification Algorithm will be lead on the first band and we can later merge them to one file as is shown in ``Out [37]``.

### In[38]
After some cleaning I used an opencv-python algorithm to identify the plants on the map, and used DBSCAN as my classification algorithm to put them into clusters where every cluster can be considered a region and each region has its own policy.

### In[38]

Here I decided to include non renewable energy plants in the study because renewable energy represent only 14% of energy production.
``all_ene.tif`` is a 1 band tif file that contains all energy plants around Paris, France region. Following the same analysis of renewable energy I was able to identify 3 main regions where a context aware policy can be applied (``Out [80]``).
![Clustered_plants](https://user-images.githubusercontent.com/57152453/130466247-47cd77d7-eee6-4fa2-bd64-80d7b4419fc7.png)
Thus we have one more dimension, to help us come up with suitable policies, second the economic value dimension.


