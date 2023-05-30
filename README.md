# Researcher Degrees of Freedom in Methodological Simulation Studies: An Illustration from Medical Statistics



## Deployment 

The execution of the `global.R` file provides the user with the results and figures of this project. The parameters of the data-generating mechanism can be adjusted here. The default number of iterations is set to 1, however, the project results contain 10000 iterations.

The computation time is extremely high.
Therefore, it is advised to at least read in the raw simulation results `sim_methods.RDS` before executing the `global.R` file.


## Repository structure

This repository is structured into a code file, a results file and a figures file.
The code file includes all scripts and functions necessary to execute this simulation study including the plotting of relevant figures. 
The simulation results are saved in the results file, whereas the plots are saved in the figures file.

`global.R`: This is the deployment file. By running this file the simulation study along with the figures is computed. Further, changes in the parameters, cores, and iterations can be made here. 

`computation_time.csv`: This .csv table contains some information on the elapsed time of the data-generating mechanisms that have been collected throughout this project.


### code

* `data_generation.R`: This .R file is responsible for generating the simulation data and calculating the performance measures on that data. Each combination will generate `n_sim` datasets and the corresponding performance measures. The execution of this file will take quite some time.

* `sim_aggregation.R`: This .R file aggregates the simulations generated by `data_generation.R` in one data.table object while calculating the rejection rate among others.

#### functions

* `function_data_generation.R`: This function generates one data set according to the provided parameters, which are be the sample size, the number of categories, and the probability distribution in treatment and control group.

* `function_method_performance.R`: This function calculates the performance measure for ten methods of the data provided, which is generated by `function_data_generation.R`.

### results

* `sim_methods.RDS`: The simulated raw data generated by `data_generation.R` is saved in a list split into the parameters of the data-generating mechanism. 

* `simulation.RDS`: The aggregated raw data with rejection rates is saved in this large data.table object computed by `sim_aggregation.R`. This .RDS file can be used for visualisations.

### figures 

The plots generated for this thesis can be found here.




