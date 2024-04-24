# Fire2a software panorama

## Contact us

| Role | Where | Contact |
| --- | --- | --- | 
| Outreach |  https://www.fire2a.com | fire2a@fire2a.com | 
| User docs |  https://fire2a.github.io/docs/ | github-issues "forum" |
| Developer docs |  https://www.github.com/fire2a | Pull Requests |
| Algorithms docs |  https://fire2a.github.io/fire2a-lib/ | Pull Requests |

## Open source software

* Cell2Fire:
	WildFire Simulator
	Command Line Interface
	https://www.github.com/fire2a/C2F-W

* Fire-ToolBox: 
	Friendly interface for Cell2Fire + Optimization and Analytics tools
	QGIS Interface(S x5)
	https://github.com/fire2a/fire-analytics-qgis-processing-toolbox-plugin

* Fire2a-lib
	Python library 
	https://github.com/fire2a/fire2a-lib

## Description Features & Roadmap

### Cell2Fire-W

#### Past
* Forked from Cell2Fire@github
* Only linux source code
* Only CanadaFBP
* Slow python wrapper

#### Present
* x3 firebehaviour models (CanadaFBP, Kitral, Scott&Burgan)
* Windows, Linux and MacOS* (x86_64 compiled) available releases
* Only C++ code 
* More metrics: Fireline Intensity, Flame Length, Rate of Spread, Fire Front Length, Fire Perimeter, Fire Area
* Single year focus
* CLI help abandoned (dont use `./Cell2Fire --help` go to web documentation)

#### Future
##### Features
* Portugal fire behaviour model
* Fire spotting, breaching
* Inputs AIIGrid rasters.asc + GTiff 
* Outputs some csv, some asc + GTiff
* Short term combat callback
##### Fixes
* MacOS fixes:

	Current release relies on pre-installed developer tools (Xcode & brew)
	Newer Apple M1 Darwin.arm64 support

* Parallel bug-fixes:
	Standard output is not well buffered (thread prints interrupt each other)
	Flame Lenght not reliable

### Fire-ToolBox
Research that can become a reproducible tool...

#### Past
* Not a processing plugin (was just a dialog)
* Only a Cell2Fire interface
#### Present
* A processing plugin enables 5 interfaces/integrations (dialog, batch[dialog], modeler[pipeline], python[x3], console)
* Decision Optimization Models (Integer programming for knapsacks, treatments, firebreak-placement, etc)
* Risk Metrics Calculation
#### Future
* Match input weather with output polygons timestamps
* Meteo generator (Chile)
* Clusterizer
#### Won't fix bugs
* Gurobipy in windows (Cplex works fine)
* Parallel DPV in windows (linux works fine)
* Pyomo is kinda slow (but flexible, integrates with many MIP solvers and the plugin can distributed "with batteries included" CBC solver)

### Fire2a-lib
#### Past
* all scattered and repeated everywhere 
#### Present
* A repo centralizing common methods and helpers
* QGIS (gdal, ogr) is main dependecy
* pip install git+https://github.com/fire2a/fire2a-lib.git
#### Future
* Two flavors for non-QGIS users
* pip install fire2a-lib
* unit tests everywhere...

