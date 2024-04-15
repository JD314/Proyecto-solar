<p><img alt="Nasa Space Apps Logo" width="140" height="140" src="https://www.nasa.gov/wp-content/uploads/2021/07/space_apps_003.png" align="left" hspace="15px" ></p>


<h1>Helios</h1>

----
<p> <b>Challenge: </b>Save the Earth from another Carrington Event!</p>
<div align="right">
<font size=3>
 <br><br>
  
</font>
</div>


<h5><b>The challenge: </b></h5>If a major space weather event like the Carrington Event of 1859 were to occur today, the impacts to society could be devastating. Your challenge is to develop a machine learning algorithm or neural network pipeline to correctly track changes in the peak solar wind speed and provide an early warning of the next potential Carrington-like event

<h5><b>Background: </b></h5>
The Carrington Event of 1859 was perhaps the most intense solar event of the century. During this event, a series of powerful coronal mass ejections hit Earth head-on. The resulting effects were observed worldwide and observations of glowing night sky auroras were recorded globally, including near the equator. This space weather event caused geomagnetically induced currents in long stretches of the telegraph transmission lines that were common in that day, generating enough current for the lines to operate without batteries. Some telegraph stations even caught fire from the induced currents. There were no high voltage (HV) electrical power transmission lines back then, so fortunately, the impact of the Carrington Event on global safety and economics was minor.

In today's world, however, where nearly everything relies on electricity and computers and machines powered by the “grid,” such an event would be disastrous! Solar storms can eject large amounts of high energy particles as solar wind, and when these winds reach Earth, they can damage telecommunications satellites, power lines, and other electrical or electronic systems. The HV power lines and substations we depend on could potentially be damaged or put out of commission for months or years, since the lead time to obtain such large power transformers is very long and they are expensive items to replace.

The Deep Space Climate Observatory (DSCOVR) is the National Oceanic and Atmospheric Administration (NOAA) Space Weather Prediction Center's principal asset for monitoring space weather and providing early warnings of solar events that could affect Earth. DSCOVR successfully launched in February 2015. It was built by NASA and is operated by NOAA. DSCOVR sits at the Sun-Earth L1 Lagrange point about one million miles away from Earth, and can warn us about 45 minutes in advance of a space weather event. DSCOVR uses a variety of instruments to detect solar activity and flares. One critical DSCOVR instrument in use since 2015 is the Faraday Cup (FC), which tracks the peak solar wind speed.

The graphical interface is available here  https://bit.ly/3rsCVsU 

Initially we considered taking the route proposed by NASA for the development of the challenge, which consisted of using a "black box" ML algorithm that consisted of using the data from the Wind probe to validate the data from the DSCOVR satellite with the objective of recalibrating data produced by noise in the Faraday cup; This route was later discarded because the method was complex and inefficient, since the resources of the challenge were available, it was clear that the existing algorithm, saturated with conditionals, would not be worth fixing, and the data used from DSCOVR was too dirty, so we opted for an alternative method using other satellites in which we could have a cleaner and more optimal data to use in a neural network, with the added benefit that it would add more reaction time to the alert because these satellites receive data from the sun by photons and not by plasma (slower) as if it does the DSCOVR. This method consists in the fact that when an EMC occurs, by means of the analysis of the Lasco coronagraph image, plasma flow properties can be obtained long before the DSCOVR does it, additionally the Goes 16 satellite detects the X-ray flux produced while the EMC occurs, Thus, using an ML algorithm and adjusting the inputs with the Lasco analysis and the GOES X-ray flux, an output categorized in 6 levels according to the intensity index (Kp) proposed by NOAA (from G0 to G5) can be given, from which the danger posed by the EMC can be conditioned.
The algorithm used consists of a random forest classification method which was trained with historical data; after training, an accuracy of 60% was achieved; this algorithm can be improved with optimization methods in the presentation of the variables.

Helios.ipynb contains the code base and the algorithm training for prediction


