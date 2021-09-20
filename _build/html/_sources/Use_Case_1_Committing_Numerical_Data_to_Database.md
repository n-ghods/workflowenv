Committing Numerical Data to a Database (from a Simulation) 
======================

## Use-Case description

Sub-System: LIGGGHTS (distributed by DCS Computing GmbH)

This use case describes how to commit data (incl. the metadata, simulation's input and reference parameters, all the simulation output files -either heavy raw outputs or averaged outputs-, and the status/validity of the results) to a database to be later used in a workflow management tool, e.g., to calibrate DEM models.


| Section                             | Comment                                                      |
| ----------------------------------- | ------------------------------------------------------------ |
| Use Case Name                       | Committing numerical data to database                        |
| Scope                               | Loading information about data and metadata and transfer to a database |
| Level                               | Top-Level data submission                                    |
| Primary Actor                       | Researchers who wants to calibrate a DEM model, or analyse data of DEM simulations |
| Stakeholders and Interests          | Researchers who perform DEM simulations or develop DEM models, experimentalists who conduct tests for calibration of DEM models |
| Preconditions                       | All the required input files, log files and outputs of the DEM model are available (DEM simulations are finished) |
| Success Guarantee                   | Accessing and committing data to the database is completed without error. Data is available in the database |
| Main Success Scenario               | Meta data file is created successfully                       |
| Extensions                          | -                                                            |
| Special Requirements                | none                                                         |
| Technology and Data Variations List | Standard input/output/log files of LIGGGHTS                  |
| Frequency of Occurrence             | after every successful LIGGGHTS simulation run               |
| Miscellaneous                       | -                                                            |

## Workflow description

In order to store any numerical data to the data base, first a **metadata** file should be created to store the essential information about the committed data. For this aim, critical information about each submitted numerical dataset is obtained form the *logfile* of the executed simulation and is written to a ***metadata.json*** file with a unique identifier (uuid). This is done by "metadatawriter" python script.

The data are mainly categorized based on their flow situations, in the database and structured as below:

**Master Layout:** database_CALIPER/<**flow situation**>/

for instance: 

- database_CALIPER/**shearLE_01**


- database_CALIPER/**uniComp_01**/


And then are stored based on the different properties: database_CALIPER/<**flow situation**>/<**main geometrical feature of the situation**>/<**particle prop 1**>/<**particle prop 2**>/<**softwareShortCut_first 7-digit uuid**>

e.g. :database_CALIPER/shearLE_01/phi_0.990/fric_0.00/nu_0.00/lig_shortuuid/

