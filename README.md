# ResearchPoster
Climate change affects human migration, often subtly. While extreme events like hurricanes can directly displace people, other factors like prolonged droughts can indirectly influence migration decisions. Although not the primary cause of migration, climate has historically shaped settlement patterns and continues to do so.

- Measure large-scale human migrations post-climate disasters through satellite imagery.
- Use Deep learning techniques to detect migration trends linked to climate events.
- Help make better plans to support those affected by climate changes.

Our data collection involves two types of information: first, satellite remote sensing imagery that shows population movement over time; second, historical climate data specific to the region and time of migration.

To process this data, we utilize GIS systems such as **ArcGIS**. Specifically, we employ **Tiled Processing** to efficiently manage large datasets. Additionally, we explore fundamental spatial patterns (signals), analyze climate data, and identify migration trends. Through this analysis, we can determine whether climate events  induce migration.

Following data preprocessing, we obtain multilayer images that represent movement or changes over time.

In the **CNN Branch**, we input images, extract features using convolutional layers, downsample the feature map (which identifies specific image features), and proceed with additional convolutional layers. The resulting output represents local advanced spatial patterns.

Simultaneously, we process the same input images in the **Transformer Branch** by dividing them into patches. Each patch is transformed into a higher-dimensional vector representation. These embeddings are then fed into Swin Transformer blocks, which compute attention within local windows. The alternating shifted window configuration enables capturing global input information. Between transformer blocks, patch merging layers adjust image dimensions while enhancing embedding dimensions. The final result comprises global features, such as trends over time.

By combining local and global features, we input the result into a multilayer perceptron (a fully connected network). Subsequently, we generate predictions using the SoftMax function. These predictions can be visualized using time series plots or heatmaps, revealing population movement following a specific climate event.

- Satellite imagery will reveal the scale and direction of population movements post-disaster.
- Identify spatial patterns (Signal) that correlate with climate change impacts.
- Our model will uncover migration trends and their correlation with specific climate events.
- Provide insights to create effective support for climate-affected populations.
