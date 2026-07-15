---
map_height_y: 2160
map_width_x: 3840
scale_pixels: 268
scale_pixels_range: 25
mapCalc1: 0.09328358208955223
---

> [!NOTE]- Quick Calculator  
> Map Height in Pixels: `INPUT[number:map_height_y]`  
> Map Width in Pixels: `INPUT[number:map_width_x]`  
> lat: `VIEW[{map_height_y} / 2][math]`  
> long: `VIEW[{map_width_x} / 2][math]`  
> How Many Pixels In Scale: `INPUT[number:scale_pixels]`  
> How Many Units in Scale: `INPUT[number:scale_pixels_range]`  
> Scale: `VIEW[1/({scale_pixels}/{scale_pixels_range})][math:mapCalc1]`


```base
filters: file.hasProperty("marker")
views:
  - type: leaflet-map
    name: Map
    mapName: test
    image: assets/world_map.png
    bounds: [[0,0], [2160, 3840]]
    minZoom: -1.5
    maxZoom: 2
    defaultZoom: -1.5
    zoomDelta: 0.5
    scale: 0.09328358208955223 ### Real units/px (resolution) of your map
    height: 500
    unit: mil

```

