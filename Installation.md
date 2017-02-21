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

