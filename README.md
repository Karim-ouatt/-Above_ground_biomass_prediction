# Above Ground Biomass Calculation Version 2
## Description
Aboveground biomass (AGB) represents to the total mass of living plant material found above the soil surface within a given area. This includes all parts of the plants that are above ground, such as stems, leaves, branches, flowers, and fruits. AGB is an important ecological and agricultural metric because it represents the amount of biological material produced by plants, which can be a key indicator of the health and productivity of an ecosystem or agricultural system.

Estimating aboveground biomass is essential for understanding and managing ecosystems, mitigating climate change through carbon sequestration. Advances in remote sensing technologies and the development of allometric equations have greatly improved the accuracy and efficiency of biomass estimation, enabling better monitoring and management of natural resources on a global scale. 

## Methodology
This work follows is about the building of an AI model for biomass calculation using the mean values of satellite images (bands), namely Sentinel 2 via the Copernicus platform. In fact, given the high correlation between the mean values of the bands, we used a dimension reduction technique called non-linear dimension reduction technique called t-distributed Stochastic Neighbor Embedding (TSNE) combined with several vegetation indices.

This technique allows us to generate a probabilistic distribution where distances between data points become probabilities. Considering a point $x_{i}$, the distance between this point and its neighborhood will be represented by a conditional probability $p_{i,j}=P(x_{j}/x_{i})$ that the point $x_{j}$ is in the neighborhood of $x_{i}$. For distinct pairs of points, if the conditional probabilities are similar, then these points will be in the same cluster. 

We applied the TSNE approach to the mean values of the bands with the 5 components to which we added vegetation indices calculated on the mean values of the bands. We obtained the 5 optimal components by the Elbow method on the whole dataset. Then, we training dataset contains the 5 components and the vegetation indices values calculated from the mean values of the bands.

## Results
After testing this approach, we obtained a RMSE of around 48 on the test dataset and the model is more or less able to generalize over prediction data. Following evaluation of the TSNE model obtained, we produced the map below giving an overview of biomass distribution over the whole country (CI). From this map, we are able to identify certain zones, such as the Tai forest, the city of Abidjan and the Banco forest. These results are very encouraging. However, we can observe a large zone with high biomass values just above the Abidjan region, extending as far as the south-east of CI. From our point of view, this can be explained by the fact that this zone contains some stretches of forest and also represents a large agro-forestry zone of the country, i.e. palm, rubber and cocoa plantations, etc.

![Biomass_Map_new2](https://github.com/Karim-ouatt/Above_ground_biomass_prediction/assets/172601303/4a7ea12e-e63a-4bca-8d33-352c25b7ad94)
