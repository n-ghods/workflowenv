
Creating, storing and exploring relational data-nodes in DB (from literature)
======================

## Use-case description

Sub-System: python3 (workflow environment: i.e. orange3)

This use case describes how to create relational data-nodes (e.g. any empirical or theoretical equations reported in literature) in the database, store the data and metadata, explore committed relational data, and retrieve them.


| Section                             | Comment                                                      |
| ----------------------------------- | ------------------------------------------------------------ |
| Use Case Name                       | Creating, storing and exploring relational data-nodes in DB  |
| Scope                               | Loading equations and related metadata in the database       |
| Level                               | Top-Level data submission                                    |
| Primary Actor                       | Researchers who wants to calibrate a DEM model (a master or Ph.D. students who has done literature review on useful relations which can be utilized in any calibration steps) |
| Stakeholders and Interests          | Researchers who explore the results of the DEM simulations or develop calibration workflows, or experimentalists who conduct tests for calibration of DEM models |
| Preconditions                       | The required metadata about the equation is available (e.g. the author(s), DOI of the article, the relational equation, etc.) |
| Success Guarantee                   | Accessing and committing data to the database is completed without error. Data-node is available in the database. |
| Main Success Scenario               | Meta data file is created successfully                       |
| Extensions                          | -                                                            |
| Special Requirements                | none                                                         |
| Technology and Data Variations List | -                                                            |
| Frequency of Occurrence             | Whenever an input from or comparison with literature data is necessary in the calibration process. |
| Miscellaneous                       | -                                                            |

## Workflow

This feature is a python3 package developed by Richard Amering, as a part of his bachelor project. This package includes several modules, such as relationalData and numericalData, along with their specific metadata classes. 

It also includes a high-level database interface to store and retrieve data-nodes to and from file-system. The dataFactory module make it possible to create both types of data nodes from either python-functions or numeric collections.

For instance, one can create relational data node from an equation/correlation, given in literature:

```python
from math import pi, log as ln

def CantorCompactionEqu6(phi, phi_0, phi_max, alpha, b, k, Z_0):
    P_star = (
        - b*phi/(2*pi) * (Z_0 + k*(phi-phi_0)**alpha) *
        ln((phi_max-phi)/(phi_max-phi_0)))
    return P_star

from pkg import DataFactory
equation_one = DataFactory.from_relation(CantorCompactionEqu6)
print(equation_one.metadata)
#or update data:
equation_two = DataFactory.from_relation(
    CantorCompactionEqu6,
    name="equ2", creator="Richard",
    author="Cantor", doi="10.1103/PhysRevLett.124.208003")

```

 

