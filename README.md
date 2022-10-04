Helios

The graphical interface is available here  https://bit.ly/3rsCVsU 

Initially we considered taking the route proposed by NASA for the development of the challenge, which consisted of using a "black box" ML algorithm that consisted of using the data from the Wind probe to validate the data from the DSCOVR satellite with the objective of recalibrating data produced by noise in the Faraday cup; This route was later discarded because the method was complex and inefficient, since the resources of the challenge were available, it was clear that the existing algorithm, saturated with conditionals, would not be worth fixing, and the data used from DSCOVR was too dirty, so we opted for an alternative method using other satellites in which we could have a cleaner and more optimal data to use in a neural network, with the added benefit that it would add more reaction time to the alert because these satellites receive data from the sun by photons and not by plasma (slower) as if it does the DSCOVR. This method consists in the fact that when an EMC occurs, by means of the analysis of the Lasco coronagraph image, plasma flow properties can be obtained long before the DSCOVR does it, additionally the Goes 16 satellite detects the X-ray flux produced while the EMC occurs, Thus, using an ML algorithm and adjusting the inputs with the Lasco analysis and the GOES X-ray flux, an output categorized in 6 levels according to the intensity index (Kp) proposed by NOAA (from G0 to G5) can be given, from which the danger posed by the EMC can be conditioned.
The algorithm used consists of a random forest classification method which was trained with historical data; after training, an accuracy of 60% was achieved; this algorithm can be improved with optimization methods in the presentation of the variables.

Helios.ipynb contains the code base and the algorithm training for prediction

