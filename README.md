## SWECO25 [![Hits](https://hits.seeyoufarm.com/api/count/incr/badge.svg?page=1&size=20&url=https%3A%2F%2Fsandbox.zenodo.org%2Fcommunities%2Fsweco25%2F&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false)](https://hits.seeyoufarm.com)

SWECO25 is a 25-meter resolution raster database for ecological research in Switzerland gathering 5,265 layers on 10 main environmental categories.

Layers available in SWECO25 were standardized using a common spatial grid covering all of Switzerland so they all share the same spatial resolution, extent, and projected coordinate reference system. The SWECO25 database includes both the standardized sources and derived layers, such as those obtained by computing focal statistics or distance functions. The SWECO25 database is openly available on Zenodo.


[![Download ](https://custom-icon-badges.herokuapp.com/badge/-DOWNLOAD%20SWECO25-blue?style=for-the-badge&logo=download&logoColor=white "Go to SWECO25 Zenodo repository")](https://sandbox.zenodo.org/communities/sweco25/)


## Spatial characteristics
| Parameter  | Value |
| ------------- | ------------- |
| GCS                         | CH1903+ / LV95 ( [EPSG:2056](https://epsg.io/2056)   )          |
| Extent                      | 2480000, 2840000, 1070000, 1300000     |
| Grid                        | Swiss-wide, [SWECO25 standard grid](https://github.com/NKulling/SWECO25/blob/main/data/SWECO25-standardgrid.tif)      |
| Spatial resolution (meters) | 25, 25  (x, y)                         |

## Layer processing

Individual layers from selected datasets were processed following an  eight-step standardization procedure:

1. rasterization of vector  layers
2. reprojection to the CH1903+ / LV95 geographic reference system
3. resampling to a common spatial grid of 25-meter resolution
4. transformation of discrete data to continuous ones (e.g. from discrete  land use and cover classes to percentage cover)
5. computation of  distance statistics for linear features (e.g., Euclidean and path  distance to roads or rivers)
6. computation of focal statistics by  applying a cell-level function calculating the average value in a  circular moving window of 13 radii ranging from 25m to 5km
7. conversion of decimals to integer values (multiplied by 100 and rounded) for storage efficiency purposes
8. saving the final raster layers as GeoTiFF files and generating metadata

For more details on the standardization procedure and [focal](https://github.com/NKulling/SWECO25/tree/main/focal_statistics_toolbox) or [distance](https://github.com/NKulling/SWECO25/tree/main/distance_toolbox) statistics computation see the [R-code](https://github.com/NKulling/SWECO25/tree/main/layer_standardization_example) and ArcGIS toolboxes.

