<h1> Fire2a Open Source Panorama </h1>

# Contact us

| Role | Where | Method |
| --- | --- | --- | 
| Outreach |  https://www.fire2a.com | fire2a@fire2a.com | 
| User docs |  https://fire2a.github.io/docs/ | github-issues "forum" |
| Algorithms docs |  https://fire2a.github.io/fire2a-lib/ | Pull Requests |
| Developer docs |  https://www.github.com/fire2a | Pull Requests |


# Overview
__1. Cell2Fire:__  
- WildFire Simulator  
- Command Line Interface  

__2. Fire-ToolBox:__  
- Friendly interface for Cell2Fire + Optimization and Analytics tools, etc.  
- QGIS Interfaces (x5)  

__3. Fire2a-lib:__  
- Algorithms and common GIS tasks Python library  

# History, Features & Roadmap

## 1. Cell2Fire-W

### Past
* Forked from Cell2Fire@github
* Only CanadaFBP
* Only linux source code (user must compile before use)
* Slow Python wrapper

### Present
* x3 firebehaviour models (CanadaFBP, Kitral, Scott&Burgan)
* Windows, Linux and MacOS* (x86_64, auditable & automated compilation) ready to use downloadable releases
* Only fast C++ code 
* More metrics: Fireline Intensity, Flame Length, Crown/Surface fractions
* Single year focus
* CLI help abandoned (dont use `./Cell2Fire --help` go to web documentation)
* Stopping early is confusing, simpler by cutting you weather.csv

### Future

#### Features
* Portugal fire behaviour model
* Fire spotting, breaching
* Inputs AIIGrid rasters.asc + GTiff 
* Outputs some csv, some asc + GTiff
* Short term combat callback
* CO2 estimation
* Slow Python only version to be available in regular QGIS repo store? (no compiled code allowed)

#### Fixes
* MacOS release relies on pre-installed developer tools (Xcode & brew)
* Apple M1 Darwin.arm64 support
* Parallel bug-fixes:

	Standard output is not well buffered (thread prints interrupt each other, unlikely but was happened)  
	Flame Lenght not reliable


## 2. Fire-ToolBox
_mantra: research that can become a reproducible tool..._

### Past
* Not a processing plugin (was just a dialog)
* Only a Cell2Fire interface

### Present
* A processing plugin enables 5 interfaces/integrations (dialog, batch[dialog], modeler[pipeline], python[x3], console)
* Decision Optimization Models (Integer programming for knapsacks, treatments, firebreak-placement, etc)
* Risk Metrics Calculation

### Future
* Match input weather with output polygons timestamps
* Meteo generator (Chile)
* Documentación en Español (Junio)
* Clusterizer, etc.
  
### Won't fix bugs
* Gurobipy in windows (Cplex works fine)
* Pyomo is kinda slow (but flexible, integrates with many MIP solvers and the plugin can distributed "with batteries included" CBC solver)
* OneDrive, Google Drive or network drives causes all kind of issues...

### Couldn't fix bugs
* Cancel button won't stop pyomo optimization: close the solver window (or kill the process) manually; also it has a timelimit by default...

## 3. Fire2a-lib

### Past
* everything, everywhere all scattered and repeated
  
### Present
* A repo centralizing _most_ algorithms and common GIS tasks used by the Fire-toolbox and Fire-Res researchers
* QGIS (gdal, ogr) is main dependecy
* pip install git+https://github.com/fire2a/fire2a-lib.git (needs github credentials)

### Future
* Two flavors for non-QGIS users
* pip install fire2a-lib (register in PyPI authority)
* unit tests (pytest) and deploy action

made by fdobad@github
