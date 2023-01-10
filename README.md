# 2-DRLP

This repository includes the MATLAB codes for the simulations in **[Using affine policies to reformulate two-stage Wasserstein distributionally robust linear programs to be independent of sample size][paper_link]**.

## 1. Requirements
To run our codes, the following softwares must be installed:
- **[MATLAB][MATLAB]**
- **[CPLEX Optimization Studio][CPLEX]**
- **[MOSEK][MOSEK]**

which are free for students and academics. Regarding their versions, we use R2019a, 12.10, and 9.3, respectively. 

## 2. File Description
### 2.1 MAT-files 
The folder has three MAT-files containing the system parameters and forecast data:
`6bus.mat`, `24bus.mat`, and `118bus.mat` for the 6-, 24-, and 118-bus test systems, respectively.
### 2.2 Script files
The folder has 18 script files. The script files `Proposed.m`, `model_M.m`, `model_K.mat`, `model_N.mat`, `model_C.m`, `model_S.m`, and `model_R.m` are run to obtain solutions to the proposed UC model, "MUC", "KUC", "NUC", "CUC", "SUC", and "RUC", respectively. The script file `comparisons.m` is run to compare the cost performances of the solutions. The remaining script files are included in one or more of the aforesaid script files and automatically run. 

## 3. Simulations 
### 3.1 Comparison via Random Sampling 

1. Run `Proposed.m` to obtain 50 sample sets of forecast error and 50 corresponding solutions to the proposed UC model. 
2. Run the other script files except `comparisons.m` to obtain solutions to the other UC models. 
3. Run `comparisons.m` to compare their out-of-sample cost performances. 
4. Repeat Steps 1-3 for different numbers of training samples `J` (line 3 in `Proposed.m`).

### 3.2 Comparison Using Real Data

The UC models can be compared on the 118-bus test system similarly, for training and test distributions of forecast error that are constructed as described in the manuscript with the one-year wind and solar power data in `118bus.mat`. 

[paper_link]: https://arxiv.org/abs/2301.00191
[MATLAB]: https://matlab.mathworks.com
[CPLEX]: https://www.ibm.com/products/ilog-cplex-optimization-studio
[MOSEK]: https://www.mosek.com/
