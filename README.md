# river-swim
SWMM + HEC-RAS automatic coupling.  [May or may not actually happen.  For the moment this is a skeleton project which has been created
mostly to have a place to put the #Functionality section.]

# Installation

Clone this project with `git clone --recurse-submodules https://github.com/larflows/river-swim`.  The `--recurse-submodules` flag is necessary in order to also clone PyRASFile, which will be localed in the `ras_file/` subdirectory.

The project is only tested with Python 3.  It may or may not work with Python 2.

# Research Question

???

# Functionality

Intended functionality.  Not all of this may be implemented.  At the time of writing (11/25/2019), none of it is (aside from pre-existing functionality in PyRASFile) and the project may or may not go forward.

## Critical Functionality

The critical functionality allows a user to feed SWMM outputs into HEC-RAS with minimal manual intervention--write SWMM outputs to a CSV, read that into HEC-RAS (or skip the CSV intermediary by using Python data structures).  This level of functionality is partial automation that makes things easier but is not very streamlined.

* HEC-RAS input and output file management: turn inputs in generic formats (CSV files, Python data structures, etc) into HEC-RAS input files and edit project files to reflect this.  Parse HEC-RAS output files into generic formats.  It would be preferable to be able to parse the simulation output files directly as report generation is very slow.  This is the responsibility of PyRASFile, and what is currently missing will be implemented in PyRASFile.  PyRASFile basically serves as a data source-agnostic coupling layer for HEC-RAS, which can be used with any input source, or as an input source to anything, as long as one creates a library to do the translation on the other end.  PyRASFile itself is designed to communicate through either CSVs or Python data structures.
  * Status: partial implementation brought over from PyRASFile.  Capable of creating flow input files, but minor manual edits to the project file are required in order to use them.  Capable of parsing the report file, but not the simulation outputs directly.
* SWMM input and output file management: as with HEC-RAS, but for SWMM.  Likewise communicate with CSV and Python data structures.  This functionality may exist in PySWMM; if not, it should also get its own project used via submodule.
  * Status: not implemented.

## Important Functionality

The important functionality fully automates the process from the command line.  Set up SWMM inputs (ideally allowing for doing so as CSVs), specify how the coupling should work, run, and get HEC-RAS outputs as CSVs.  No user intervention after initial configuration.  However, initial configuration includes e.g. specifying geometry in HEC-RAS etc; the coupling is meant to focus on timeseries, not river setup etc.

* Simple user specification (e.g. in config file) of how to couple SWMM and HEC-RAS, what inputs to use, and what outputs to retrieve.
  * Status: not implemented.
* Automatically run SWMM.  Presumably PySWMM has this.
  * Status: not implemented, but probably available in PySWMM.
* Automatically run HEC-RAS.  The only documented means to do this is in Excel VBA and the HEC-RAS API is otherwise undocumented.
  * Status: not implemented.
* Automatically run the whole thing from the config file etc.
  * Status: not implemented.

## Convenience Features

The convenience features make life easier but are not at all critical or terribly important.

* Convert between SWMM and HEC-RAS geometry so the user only has to specify it once.  Not sure how feasible this is.
  * Status: not implemented.
* Automatically generate design storms and other useful timeseries data from simpler inputs.
  * Status: not implemented.
* GUI
  * Status: not implemented.