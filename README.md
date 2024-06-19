# Above Ground Biomass Calculation Version 2
## Description
Aboveground biomass (AGB) is defined as the total mass of living plant material found above the soil surface in a particular area. This covers all components of the plant that grow above earth, such as stems, leaves, branches, flowers, and fruits. AGB is an important ecological and agricultural metric since it represents the amount of biological material produced by plants, which can be a good indicator of an ecosystem's health and production.

Estimating aboveground biomass is critical for understanding and preventing climate change by carbon sequestration. Indeed, plants absorb carbon dioxide (CO₂) from the atmosphere through photosynthesis and store it in their tissues. AGB estimates are essential for calculating the amount of carbon stored in vegetation.

Advances in remote sensing technologies and the development of allometric equations have significantly improved the accuracy and efficiency of biomass estimation, enabling better global monitoring and management of earth's resources.

## Methodology
This work focuses on developing an AI model for biomass calculation utilizing the mean values of satellite images (bands), namely Sentinel 2 via the Copernicus platform. Given the high correlation between the mean values of the bands, we applied a non-linear dimension reduction technique known as t-distributed Stochastic Neighbor Embedding (TSNE) combined with with multiple vegetation indices.

TSNE technique generates a probabilistic distribution in which the distances between data points are converted into probabilities. A conditional probability $p_{i,j}=P(x_{j}/x_{i})$ indicates that a point $x_{j}$ is in the neighborhood of $x_{i}$. If the conditional probabilities of two independent pairs of points are similar, they will be in the same cluster. We obtained five optimum components for the algorithm by the Elbow method on the whole dataset. The training dataset then contains the five components as well as the vegetation index values calculated using the mean values of the bands.

## Results and perspectives
After evaluating this approach, we found an RMSE of roughly 48 on the test dataset, indicating that the model can more or less generalize to prediction data. Following the evaluation of our model, we created below a biomass map across CI, which provides an overview of biomass distribution across the country. This map allows us to identify certain zones, such as the Taï National Park, the city of Abidjan, and the Banco forest. These results are really encouraging. However, we can see a wide zone with high biomass values right over the Abidjan region, which extends as far as the south-east of CI. 
This can be explained by the fact that this zone has some stretches of forest as well as among the vast agro-forestry zones of the country, which includes palm, rubber, and cocoa plantations, among other things. The model tends to assign high value of biomass to any dense vegetation area. In our future work, we are going to investigate additional aproaches to improve the accuracy of the existing model.


![Biomass_Map_new2](https://github.com/Karim-ouatt/Above_ground_biomass_prediction/assets/172601303/4a7ea12e-e63a-4bca-8d33-352c25b7ad94)
