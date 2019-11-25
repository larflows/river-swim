# river-swim
SWMM + HEC-RAS automatic coupling.  [May or may not actually happen.]

# Functionality

Intended functionality.  Not all of this may be implemented.  At the time of writing (11/25/2019), none of it is and the project may or may not go forward.

## Critical Functionality

* HEC-RAS input and output file management: turn inputs in generic formats (CSV files, Python data structures, etc) into HEC-RAS input files and edit project files to reflect this.  Parse HEC-RAS output files into generic formats.  It would be preferable to be able to parse the simulation output files directly as report generation is very slow.
  * Status: partial implementation brought over from PyRASFile.  Capable of creating flow input files, but minor manual edits to the project file are required in order to use them.  Capable of parsing the report file, but not the simulation outputs directly.
