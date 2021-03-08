# Leaflet Draggable Popup

This is a Leaflet plugin for create draggable popup with a tail point to anchor. Feedback appreciated !

## Online demo

<https://wushengcq.github.io/demo/draggable-popup/index.html>

![example screenshot](/demo/screenshot-1.png)

## How can I use it?

1. Import the plugin js file in your page. 

2. The following code will create three draggable popups, two of them are standalone lables, and one is popup bind to a marker.

```javascript

 addPopup(L.latLng(30.661057, 104.081757), {'closeButton':'true'}, L.latLng(34, 100));
 addPopup(L.latLng(32.047615, 118.772781), {'backgroundColor':'#8ac4d0'});
bindPopup(L.latLng(34.668041, 112.424797), {'backgroundColor':'#fce38a', 'closeButton':'true'});

function addPopup(anchorLatLng, options, popupLatLng) {
	var popup = L.draggablePopup(options)
		.setAnchorLatLng(anchorLatLng)
		.setPopupLatLng(popupLatLng ? popupLatLng : anchorLatLng)
		.setContent('<p style="color:red">' + anchorLatLng + '</p>')
		.addTo(_map);

	var marker = L.circleMarker(anchorLatLng, {
		radius: 5
	}).addTo(_map);
}

function bindPopup(anchorLatLng, options, popupLatLng) {
	var popup = L.draggablePopup(options)
		.setAnchorLatLng(anchorLatLng)
		.setPopupLatLng(popupLatLng ? popupLatLng : anchorLatLng)
		.setContent('<p style="color:red">' + anchorLatLng + '</p>');

	var marker = L.circleMarker(anchorLatLng, {
		radius: 5
	}).addTo(_map).bindPopup(popup);
}

```

