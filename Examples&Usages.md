## 4. Minimal working example
### 4-1. heatmap layer
히트맵 레이어 설명

  - locations - Iterable of (latitude, longitude) pairs showing a specific location. This locations can be input as either a list of tuples or a twodimensional array or a dataframe. First comes considered as latitude and second comes considered as longitude. Latitudes are expressed as a float between -90 and +90. Longitudes are expressed as a float between -180 and +180. 
  - weights (iterable of floats, optional) – Iterable of weights of the same length as locations. It is possible to give weight using this. All the weights must be positive.
  - max_intensity (float, optional) – Strictly positive floating point number indicating the numeric value that corresponds to the hottest colour in the heatmap gradient. Any density of points greater than that value will just get mapped to the hottest colour. Setting this value can be useful when your data is sharply peaked. It is also useful if you find that your heatmap disappears as you zoom in.
  - point_radius (int, optional) – Control the size of point to be shown. All the values must be positive This determines the “radius of influence” of each data point.
  - dissipating (bool, optional) – When user zooms in or out, the radious of influence can be changed. In case it is True, the influence will be increased as user zooms out or decreased zoom in. If you do not want it and keep the influence same, make it False. Default value is True.
  - opacity (float, optional) – The opacity of the heatmap layer. Defaults to 0.6.
  - gradient (list of colors, optional) – This data type should be a list of colors. User can control the color gradient. Google Maps choose proper  color by  linear interpolation. Colors can be specified as a simple string, e.g. ‘blue’, as an RGB tuple, e.g. (100, 0, 0), or as an RGBA tuple, e.g. (100, 0, 0, 0.5).

## 5. 2-3 examples of typical use-cases


## 6. List other interesting or useful features (additional examples are not required)
### 6-1. Custom Control
User can magnify or diminish gmaps output customly. User can move the focus of map 
and find where they want to see just same as using google map

### 6-2. Street view and Satalite view
Not only user can move there map customly, but also user can use google maps street view service.
User can experience panorama view of real street. And also can use satellite view

### 6-3. Polygon and Poliline
With using gmaps library, User can notify specific place on the map several ways. 
One of that is making poliline or polygon by adding layer.

### 6-4. Others
And moreover, many features including Geocoding, Timezone, Elevation are there.
