Due to github's file size limits, the main volume-data tarfile is hosted on box, please download 'volume_connectomes.tar.gz' (filesize = 2.35 gb). using the following link:
https://umich.box.com/s/skhmo7twdtavdagm7h5kr93oc33sc1by

The tarfile "volume_connectomes.tar.gz" contains 12 .pickle files. 
One pickle file for each of the following combinations - {15, 7, 3 minutes} x {day 1, 2} x {5, 2 fd thresholding}

Each pickle file contains a list of subject names and the upper-triangular matrix values for the functional connectomes for these subjects.

Please extract the contents of 'volume_connectomes.tar.gz' into the current directory (Predictive_Modeling_Reliability_HCP/data/volume) using the following command:
tar -xvf volume_connectomes.tar.gz
