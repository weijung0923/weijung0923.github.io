---
title: "入門Openlayers-建立地圖(一)"
description: "This description will be used for the article listing and search results on Google."
date: "2023-06-30"
banner:
  src: "../../images/kelly-sikkema-Hl3LUdyKRic-unsplash.jpg"
  alt: "OL Post"
  caption: 'Photo by <u><a href="https://unsplash.com/photos/Nc5Q_CEcY44">Florian Olivo</a></u>'
categories:
  - "GIS"
  - "入門"
  - "Web"
keywords:
  - "GIS"
  - "Openlayers"
---

__學習Openlayers__
<br>
引入CDN和NPM兩種方式練習，但我建議初學者是使用CDN方式進行學習，可以參考官網連結或參考我提供的範例程式創建地圖

https://openlayers.org/en/latest/examples/simple.html

## HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="style.css">
  
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/ol@v7.4.0/ol.css">
  <script src="https://cdn.jsdelivr.net/npm/ol@v7.4.0/dist/ol.js"></script>
</head>

<body>
  <div id="map" class="map"></div>
  <script src="./main.js"></script>
</body>

</html>

```

## CSS
```css
body{
  padding: 0;
  margin: 0;
}

.map {
  width: 100vw;
  height: 100vh;
}

```
## JS
```JS
const map = new ol.Map({
	layers: [
		new ol.layer.Tile({
			source: new ol.source.OSM(),
		}),
	],
	target: 'map',
	view: new ol.View({
		center: ol.proj.fromLonLat([121, 23.6]),
		zoom: 8,
	}),
});
```