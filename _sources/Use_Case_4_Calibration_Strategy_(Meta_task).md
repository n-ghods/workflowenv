Deciding about the calibration strategy (Meta-task) 
======================

Use-case description 
----------------------

Sub-System: -

This use case describes how to decide on the required experiment(s)/template(s) that should be used for the specific application that the DEM-parameter calibration is performed. the calibration tests should consider the nature of the real process which should be simulated and therefore the calibration process should be selected accordingly. The target flow situation (e.g. quasi-static, slow, high dynamical bulk material flow), material characteristics (extent of deformability, plasticity, cohesiveness, ...), and the suitable contact model and its required parameters should be taken into account. Since multiple combination of parameters can produce the target bulk response in every experiment, it is highly recommended to use either more than one experiment or to aim for more than one target measured response. 


| Section                             | Comment                                                      |
| ----------------------------------- | ------------------------------------------------------------ |
| Use Case Name                       | Deciding on the calibration strategy                         |
| Scope                               | Choosing the right calibration workflow                      |
| Level                               | Top-Level calibration strategy                               |
| Primary Actor                       | Researchers who wants to calibrate a DEM model, or have previous experience and deep knowledge in particle technology and DEM simulations |
| Stakeholders and Interests          | Researchers who perform DEM simulations or develop DEM models, experimentalists who conduct tests for calibration of DEM models |
| Preconditions                       | Deep knowledge about the sensitivity of common experiments to the input DEM parameters, contact models in DEM simulations, |
| Success Guarantee                   | Accessing and committing data to the database is completed without error. Data is available in the database and the calibration workflows and optimum order of performing the experiments in calibration workflows. |
| Main Success Scenario               | The suitable workflow is selected and the prerequisites for preforming such workflow within the workflow environment is available. |
| Extensions                          | -                                                            |
| Special Requirements                | The experimental devices (data), relational data, and corresponding calibration templates should be available. |
| Technology and Data Variations List | -                                                            |
| Frequency of Occurrence             | Before performing any calibration case                       |
| Miscellaneous                       | -                                                            |

## Workflow

Based on the above-described criteria (the application and desired flow situation, contact model, particle property, etc. ), the user should choose the suitable experiments and calibration templates in the calibration workflow. Despite numerous studies and proposed workflows for the calibration of DEM parameters, there is no universal method for the calibration of DEM parameters. And the users should be very careful with defining the workflows, making sure that the group of calibrated parameters are general, since multiple combination of parameters can lead to the same bulk response in single experiments.

Here you can see a summarized illustration of some proposed workflows in recent literature:

### Dependence of Micro-Macro properties for **cohesionless** bulk material under **rapid flow conditions (>0.1 m/s)** and **low consolidation (<100 kPa)** 

Reference : [Katterfeld et al. (2019)](https://www.researchgate.net/publication/334129169_Calibration_of_DEM_Parameters_for_Cohesionless_Bulk_Materials_under_Rapid_Flow_Conditions_and_Low_Consolidation)

![usc4_1](../workflowenv/images/uc4_1.png)

![uc4_2](../workflowenv/images/uc4_2.png)



### Automatized calibration workflow for DEM models of Cohesive powders exhibiting bulk volume loss of up to 25% (after uniaxial consolidation up to 10 kPa)

Reference: [Orefice and Khinast (2019)](https://www.sciencedirect.com/science/article/pii/S0032591019310137?via%3Dihub#f0085)

**Contact model**: [adhesive elasto-plastic model](https://link.springer.com/article/10.1007%2Fs10035-008-0099-x)

![uc4_3](../workflowenv/images/uc4_3.png)

![uc4_4](../workflowenv/images/uc4_4.png)

### A standard procedure to calibrate friction coefficients in DEM Simulation of cohesionless bulk material

Ref.: [Roessler et al. (2019)](https://www.sciencedirect.com/science/article/pii/S0032591018309380?via%3Dihub)

![uc4_5](../workflowenv/images/uc4_5.png)

\*this modified draw down test is enough on its own to give a unique set of parameters

A large number of simulations are carried out, for each range of the friction coefficients and then the parameter set selected by superimposition of the response surfaces.

![uc4_6](../workflowenv/images/uc4_6.png)

### Calibration of DEM parameters of cohesive bulk materials by only using lifting of a hollow cylinder

Ref.: [Roessler and Katterfeld (2019)](https://www.sciencedirect.com/science/article/pii/S0032591018309380?via%3Dihub)

**Contact model**: Hertz with a simplified JKR cohesion model and modified elasto-plastic spring-dashpot model (Wensrich et al. 2012)

![uc4_7](../workflowenv/images/uc4_7.png)

![uc4_8](../workflowenv/images/uc4_8.png)

![uc_9](../workflowenv/images/uc4_9.png)

\* refer to the algorithm below:

![uc4_10](../workflowenv/images/uc4_10.png)

### Proposed calibration and validation method for modelling of Cylindrical Pellets

Ref.: [Marigo and Stitt (2015)](https://www.jstage.jst.go.jp/article/kona/32/0/32_2015016/_article/-char/ja/)

![uc4_11](../workflowenv/images/uc4_11.png)

![uc4_12](../workflowenv/images/uc4_12.png)