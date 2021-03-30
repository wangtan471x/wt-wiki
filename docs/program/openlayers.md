### 处理WKT格式字符串

```javascript
    var format = new ol.format.WKT();
    var feature = format.readFeature(wktData, {
        dataProjection: 'EPSG:4326',
        featureProjection: 'EPSG:3857'
    });
    var vector = new ol.layer.Vector({
        source: new ol.source.Vector({
            features: [feature]
        })
    });
    map_js.map.addLayer(vector);
```

### 处理Geojson格式字符串

```javascript
var splitfeature = new ol.format.GeoJSON().readFeature(('GeoJSON字符串'), {
    featureProjection: 'EPSG:4326' //当前坐标系
});
vectorSource.addFeature(splitfeature);

```

### openlayers获取WKT

​	https://blog.csdn.net/weixin_42547014/article/details/109234988

前提：明确矢量图形的feature

```javascript
//WKT
var wktshape = new ol.format.WKT().writeFeature(editorSource.getFeatures()[0]);

//GeoJSON
var jsonshape = new ol.format.GeoJSON().writeFeature(editorSource.getFeatures()[0]);
```


【获取刚刚画完的】

```javascript
//新建draw对象
var draw = new ol.interaction.Draw({
	 source: editorSource,  //图层的source
	 Type: 'LineString'    //图层类型'Point'/'LineString'/'Polygon'
});
draw.on('drawend', function(event) {
	if (event.feature) {
		vectorSource.addFeature(event.feature);
		console.log((event.feature.getGeometry().getCoordinates()).toString())
		var Coordinates = new ol.format.GeoJSON().writeFeature(event.feature);
		var positionList = new ol.format.WKT().writeFeature(event.feature);
	}
	map.removeInteraction(draw);
});
// 将Draw绘图控件加入Map对象
map.addInteraction(draw);
```

### Openlayers中Feature与WKT之间的转换，Feature坐标系的转换

**

```javascript
一、Feature 转WKT 且带坐标系的转换**spa

   var strwkt = new ol.format.WKT().writeFeature(feature, {
        dataProjection: targetcrs,//目标坐标系
        featureProjection:crs //当前坐标系
      });orm

 **二、WKT转Feature** get

 var newfeature = new ol.format.WKT().readFeature(strwkt);it

**三、Feature 坐标系转换（支持全部图形）**io

 var geom = feature.getGeometry().transform(crs, targetcrs);
 feature.setGeometry(geom);form

**四、利用WKT转换Feature坐标系（这种不支持GEOMETRY不为Circle）**class

 var strwkt = new ol.format.WKT().writeFeature(feature, {
        dataProjection: targetcrs,
        featureProjection:crs
      });
      var newfeature = new ol.format.WKT().readFeature(strwkt);transform

注意：方法4获得的Feature 会没有原始Feature对应的Properties
```

### 获取矢量坐标点

```
从map.layers数组中获取图层实例（OpenLayers.Layer.Vector）。遍历layer.features中的features（OpenLayers.Feature.Vector）。使用feature.geometry访问要素的几何（OpenLayers.Geometry）。这可以是任何类型的几何。
对于line，类型为OpenLayers.Geometry.LineString。使用getVertices函数获取行中所有点（OpenLayer.Geometry.Point）的数组。
```

