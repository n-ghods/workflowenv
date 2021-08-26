# Overview

The workflow environment DEMvironment has three core capabilities:

1. Preparing input data and interacting with a database
2. Performing calibration tasks of one or more parameters
3. Storing and utilizing calibrated parameters for DEM simulations

![overview](../workflowenv/images/overview.png)



Specifically, DEMvironment consists of a set of individual workforces that are centered around a certain use case of the environment.

While DEMvironment was build with [ASPHERIX(R)](https://www.aspherix-dem.com/) and [LIGGGHTS(R)](https://www.cfdem.com/liggghts-open-source-discrete-element-method-particle-simulation-code#:~:text=LIGGGHTS%20is%20an%20Open%20Source,the%20field%20of%20Molecular%20Dynamics.) as the main work horses, it can be easily equipped with adaptors for any other DEM simulation or calibration tool.

![](../workflowenv/images/aspherix_logo.png)

![](../workflowenv/images/liggghts.png) 

