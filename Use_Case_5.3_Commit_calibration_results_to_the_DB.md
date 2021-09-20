Use Case 5.3 - Commit Calibration Results to the DB
======================

## Use-case description

Sub-System:  LIGGGHTS (or Aspherix) - (distributed by DCS Computing GmbH) 

This use case describes how to commit successful calibration results to the DB.


| Section                             | Comment                                                      |
| ----------------------------------- | ------------------------------------------------------------ |
| Use Case Name                       | Commit Calibration Results to the database                   |
| Scope                               | Loading the results and metadata about each calibration case to the database |
| Level                               | Low-level calibration data submission                        |
| Primary Actor                       | Researchers who wants to calibrate a DEM model, or analyse data of DEM simulations (A PhD student or Master student who has done DEM Simulations before) |
| Stakeholders and Interests          | Researchers who perform DEM simulations or develop DEM models, experimentalists who conduct tests for calibration of DEM models |
| Preconditions                       | The UC5.2 has successfully completed.                        |
| Success Guarantee                   | Accessing and committing the calibration results is completed without error and data is available in the database. |
| Main Success Scenario               | Metadata file is created successfully.                       |
| file Extensions                     |                                                              |
| Special Requirements                | -                                                            |
| Technology and Data Variations List |                                                              |
| Frequency of Occurrence             | upon request after each calibration workflow                 |
| Miscellaneous                       | -                                                            |

## Workflow

Simply by the features of the use-case 1 and 3, the successful calibration cases can be submitted to the database. Similar to the use-case 1, the meta-data is created from the ***log_aspherix-calibration.txt*** file as well as the calibrated parameters, ***calibrated_params.txt***. 

With the above two files, one can setup any other DEM simulation with these sets of parameters. To assess the calibration workflow, the history of the quality function can be saved and then visualized within the workflow. It is not necessary to save all the working directories of all simulations, but the path to the storage location is stored in the metadata file.

