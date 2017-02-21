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

Plot data on map projections with matplotlib. An add-on toolkit for matplotlib that lets you plot data on map projections with coastlines, lakes, rivers and political boundaries


## 3. Installation instructions, platform restriction and dependent libraries 

### 3-1. Dependencies
The current version of gmaps is only tested with IPython 4.2 or later and ipywidgets 5.2.2 and traitlets 4.3.0 or later. To upgrade to the latest versions, use:
	
	$ pip install -U jupyter

Make sure that you have enabled widgets extensions to Jupyter:

	$ jupyter nbextension enable --py --sys-prefix widgetsnbextension

### 3-2. Installing gmaps
Install the Python component using:
	
	$ pip install gmaps

Then tell Jupyter to load the extension with:

	$ jupyter nbextension enable --py --sys-prefix gmaps

### 3-3. Development version
You must have NPM to install the development version. You can install NPM with your package manager.
You must also install gmaps in a virtual environment (or, at least, you must be able to run pip without root access).
Clone the git repository by running:

	$ git clone https://github.com/pbugnion/gmaps.git

Change to the project's root directory and run:

	$ pip install -e .

This will create a directory called static/ in the gmaps/ directory. This directory contains Javascript sources. Every time you change the Javascript sources, you will need to recompile this directory by re-running this command (despite everying being installed in editable mode).
You can then enable the extension in Jupyter:

	$ jupyter nbextension install --py --symlink --sys-prefix gmaps
	$ jupyter nbextension enable --py --sys-prefix gmaps
	
### 3-4. Authentication
Most operations on Google Maps require that you tell Google who you are. To authenticate with Google Maps, follow
the [instructions](https://console.developers.google.com/flows/enableapi?apiid=maps_backend,geocoding_backend,directions_backend,distance_matrix_backend,elevation_backend&keyType=CLIENT_SIDE&reusekey=true) for creating an API key. You will probably want to create a new project, then click on the Credentials
section and create a Browser key. The API key is a string that starts with the letters AI.


You can pass this key to gmaps with the configure method:

	gmaps.configure(api_key="AI...")

Maps and layers created after the call to gmaps.configure will have access to the API key.
You should avoid hard-coding the API key into your Jupyter notebooks. You can use environment variables. Add the
following line to your shell start-up file (probably ~/.profile or ~/.bashrc):

	export GOOGLE_API_KEY=AI...

Make sure you don’t put spaces around the = sign. If you then open a new terminal window and type env at the
command prompt, you should see that your API key. Start a new Jupyter notebook server in a new terminal, and type:

	import os
	import gmaps
	gmaps.configure(api_key=os.environ["GOOGLE_API_KEY"])



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

## 7. Summary and personal assessment of the library\
Until now, We have learned about gmaps from installing to usages. 
As introduced before, gmaps is a libarary which can help visualizing maps through Google maps.
We can use most of useful features of Google maps including searching, notifying and so on.
We have tried to show you as easy and specifically as we can but it could be little tricky. 
If you need more help or questions, please contact us or follow the references. 
Also you will be able to get enough infomation through internet search.
gmaps may need you API key and it could cause payment.
However this library is definitely useful and can enforce your business better

Other libararies for visualization mapping, they needs data file which contains that region's map information
and we can only see that scene
However for gmaps we can use simply by applying only lattitute and longitute information. 
And moreover we can use several useful features of Google maps.
Except for specific purpose of map visualization, I think this libarary is the most vasatile and useful, easy applicapable library. If you are free from API problem.
It will be better if this library has a function that can only show outline of the city or countries border line. 

## 8. References
1. [gmaps](https://pypi.python.org/pypi/gmaps)
2. [python-gmaps](Python official webpage - https://pypi.python.org/pypi/python-gmaps/0.3.1)
2. [basemap](https://pypi.python.org/pypi/basemap)
3. [GoogleAPIs](https://console.developers.google.com/flows/enableapi?apiid=maps_backend,geocoding_backend,directions_backend,distance_matrix_backend,elevation_backend&keyType=CLIENT_SIDE&reusekey=true)
4. [Stanford Computational Journalism Lab - Stanford Computational Journalism LabComputational Methods in the Civic Sphere](http://www.compciv.org)
5. [Github gmaps introduction](https://github.com/pbugnion/gmaps)
6. [Github gmaps introduction](https://github.com/googlemaps/google-maps-services-python)
7. [ReadDocs](https://python-gmaps.readthedocs.io/en/latest/)
8. [gmaps Documentation (Release 0.0.2) - Michał Jaworski]
