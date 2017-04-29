# cesium-terrain-push
a demo for ground-push in Cesium

inspired by [cesium-groundpush-plugin](https://github.com/NICTA/cesium-groundpush-plugin).

Thanks for the great tutorial written by [fuckgiser](http://www.cnblogs.com/fuckgiser/p/5876339.html) in Chinese.

```
var viewer = new Cesium.Viewer('cesiumContainer');
var west = Cesium.Math.toRadians(120);
var south = Cesium.Math.toRadians(30);
var east = Cesium.Math.toRadians(120.001);
var north = Cesium.Math.toRadians(30.001);
var pushRectangle = new Cesium.Rectangle(west,south,east,north);

var structure = {
    heightOffset:100.0,
    pushRectangle:pushRectangle,
    pushDepth:50
};

viewer.terrainProvider=new Cesium.EllipsoidTerrainProvider({
    structure:structure
});
```

pass a structure object to EllipsoidTerrainProvider

heightOffset: offset up from zero, meters
pushRectangle: the area to push down, as a `Cesium.Rectangle`
pushDepth: the depth to push down, meters

# Known issue
When zooming too close to the pushed region, the camera will freeze for some unknown reasons.

The soure code will be uploaded in the near future. 
