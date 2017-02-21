# GMAPS-tutorials

## 1. Motivation - one paragraph explaining the main objective of the library and the problem it is trying to solve 
GMAPS is a plugin for including interactive Google maps in the IPython Notebook. gmaps allows you to use the potential of Google Maps in a simple way. Sometimes you want to show what you want on the map. For example, the shortest route to the destination, the surrounding Starbucks and so on. In this case, you can use gmaps to display the map more easily.


## 2. Context - alternative solutions for solving the problem 

### 2-1 using leaflet maps
The current version of this library is inspired by the [ipyleaflet notebook widget extension](https://pypi.python.org/pypi/ipyleaflet) . This extension aims to provide much of the same functionality as gmaps, but for leaflet maps, not Google 

### 2-2 using google maps
There are a bunch of libraries for Google Maps Web Service. To name a few:
* [googlemaps](https://pypi.python.org/pypi/googlemaps/)
* [google.directions](https://pypi.python.org/pypi/google.directions)

What's wrong with them? googlemaps uses deprecated google API and forces
you to format your parameters instead of using native python datatypes.
And what about google.directions? Just take a look inside it's code...

So here is code for new Google Maps API endpoints. It requires
[requests](https://github.com/kennethreitz/requests) supports native python
datatypes and is sweetened with some syntactic sugar. Nothing more.
No bells and whistles.

### 2-3 using shapefiles
Also another libarary exists using shapefiles.
* [basemap](https://pypi.python.org/pypi/basemap)

Plot data on map projections with matplotlib. An add-on toolkit for matplotlib that lets you plot data on map projections with coastlines, lakes, rivers and political boundaries.

## References
1. [gmaps](https://pypi.python.org/pypi/gmaps)
2. [python-gmaps](https://pypi.python.org/pypi/python-gmaps/0.3.1)
2. [basemap](https://pypi.python.org/pypi/basemap)
3. [GoogleAPIs](https://console.developers.google.com/flows/enableapi?apiid=maps_backend,geocoding_backend,directions_backend,distance_matrix_backend,elevation_backend&keyType=CLIENT_SIDE&reusekey=true)
4. [Stanford Computational Journalism Lab - Stanford Computational Journalism LabComputational Methods in the Civic Sphere](http://www.compciv.org)
5. [Github gmaps introduction](https://github.com/pbugnion/gmaps)
6. [Github gmaps introduction](https://github.com/googlemaps/google-maps-services-python)
7. [ReadDocs](https://python-gmaps.readthedocs.io/en/latest/)
8. [gmaps Documentation (Release 0.4.0) - Pascal Bugnion](https://github.com/power9490/GMAPS-tutorials/blob/origin/Document/gmaps%20Documentation%20(Release%200.4.0)%20Pascal%20Bugnion.pdf)
