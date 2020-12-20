The tarfile "data\cifti\connectomes.tar.gz" contains 12 .pickle files. 
One pickle file for each of the following combinations - {15, 7, 3 minutes} x {day 1, 2} x {5, 2 fd thresholding}

Each pickle file contains a list of subject names and the upper-triangular matrix values for the functional connectomes for these subjects.

Please extract the contents of the tarfile into the current directory (data\volume) using the following command:
tar -xvf connectomes.tar.gz