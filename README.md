# Above Ground Biomass Calculation Version 2
## Description of what as been done
This work follows the implementation of a biomass calculation model in specific areas (CI). This model estimates biomass over the entire extent of the CI using the mean values of satellite images (bands), namely Sentinel 2 via the Copernicus platform. In fact, given the high correlation between the mean values of the bands, a dimension reduction technique called Principal Component Analysis (PCA), with several vegetation indices, were used to train an AI model.

The aim of our work is to test a number of approaches, such as another non-linear dimension reduction technique called t-distributed Stochastic Neighbor Embedding (TSNE) and the introduction of other statistics (min, max) in addition to the mean, to improve the performance of the pre-existing model, which is around 56. 

## The TSNE approach
This is an unsupervised learning algorithm that, unlike PCA, allows nonlinear dimension reduction. This technique allows us to generate a probabilistic distribution where distances between data points become probabilities. Considering a point $x_{i}$, the distance between this point and its neighborhood will be represented by a conditional probability $p_{i,j}=P(x{j}/x_{i})$ that the point $x_{j}$ is in the neighborhood of $x{i}$. For distinct pairs of points, if the conditional probabilities are similar, then these points will be in the same cluster. We replaced the PCA technique with TSNE and obtained an RMSE of around 48.

## The statistical approach
This approach consists of extracting, in addition to the mean values of the bands, the min and max values on which some vegetation indices have been calculated, in order to establish another model. We tested the TSNE approach on these new features and then evaluated the model obtained. However, this model seems less satisfactory in terms of generalization to predictive data, despite recording interesting performances of around RSME of 36 on the test dataset.

## Results
Among the approaches we tested, the one with TSNE attracted our attention the most, with an RMSE of around 48 and a generalization much closer to reality. In fact, the TSNE approach was applied to the mean values of the bands and we obtained 5 optimal components to which we added vegetation indices calculated on the mean values of the bands. 
Following evaluation of the TSNE model obtained, we produced the map below giving an overview of biomass distribution over the whole country (CI). From this map, we are able to identify certain zones, such as the Tai forest, the city of Abidjan and the Banco forest. These results are very encouraging. However, we can observe a large zone with high biomass values just above the Abidjan region, extending as far as the south-east of CI. From our point of view, this can be explained by the fact that this zone contains some stretches of forest and also represents a large agro-forestry zone of the country, i.e. palm, rubber and cocoa plantations, etc.

![Biomass_Map_new2](https://github.com/Karim-ouatt/Above_ground_biomass_prediction/assets/172601303/4a7ea12e-e63a-4bca-8d33-352c25b7ad94)
