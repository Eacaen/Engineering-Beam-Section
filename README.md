# Engineering-Beam-Section
Engineering Beam Calculation with open or closed profile
ORIGIN Project from [composite-blade-design](https://github.com/Eacaen/composite-blade-design)

# Introduction
====================

| |CN|ENG|   |
|---|----|-----|-----|
|1|`工程梁剖面剪流剪心计算`|[Engineering Beam Calculation with open or closed profile][CLT]| [Introduction](#composite-material-calculation-with-clt)|`read the program introduction for more details ` [Here](/doc/pro_introduction.pdf)  

[Running requirements](#running-requirements) | [Installation](#installation) | [License](#license) 

<img align="right"  src="fig/close_ddd2.PNG" data-canonical-src="fig/close_ddd2.PNG" />

********************************
##### Project code for shear center&flow calculation,PARTLY FINISH.
********************************

## Project goals:
- calculate the normal stress & shaer flow & shear center of open profile or close profile with single or multi-cells.
- Use the *Engineering Beam Theory* to simplify the profile geometry properities.
- Show accurate calculate information of results, display figures of  normal stress and shear flow distribution,the number of profile node , the location of shear center.

## Data flow of the Project
<img src="fig/dataflow.png" data-canonical-src="fig/dataflow.png" />

## Task achieved:
- [x] calculate normal stress & shaer flow & shear center of open profile.
- [x] calculate normal stress & shaer flow & shear center of close profile of single cell.
- [x] calculate normal stress & shaer flow & shear center of close profile of multi-cells.
- [x] plot profile with different thickness. 
- [x] plot normal stress and shear flow.
- [x] report the shear flow experssion between each two nodes.
- [ ] the profile move to its centroid when calculation, the shear center is the relavite location.
- [ ] the Project just a simple demo of the Engineering Beam calculation, the deformation like  restricted torsion didn't take into consideration.
- [ ] ...

## Brief intro
### Coordinate System
 * the input xy data is the actual loation of profile, in the calculation need the Sx=Sy=0, the Jxy=0 is not necessart.

### Calculation flow chart
<img src="fig/cal-flow" data-canonical-src="fig/cal-flow" />


### Profile shear flow&center calculation
* The main package is a Python composite materials calculation package.
The calculation of laminate stress, strain and failure Criterion based on the Classical Lamination Theory ([CLT](https://en.wikipedia.org/wiki/Composite_laminates)).  

    - normal stress in profile section,
    
    ![](http://latex.codecogs.com/png.latex?%5Csigma_z%20%3D%20%5Cfrac%7BM_yJ_x-M_xJ_%7Bxy%7D%7D%7BJ_xJ_y-J%5E2_%7Bxy%7D%7Dx&plus;%5Cfrac%7BM_xJ_y-M_yJ_%7Bxy%7D%7D%7BJ_xJ_y-J%5E2_%7Bxy%7D%7Dy&plus;%5Cfrac%7BN_z%7D%7BF%7D%3D%5Cfrac%7B%5Coverline%7BM%7D_y%7D%7BJ_y%7Dx&plus;%5Cfrac%7B%5Coverline%7BM%7D_x%7D%7BJ_x%7Dy&plus;%5Cfrac%7BN_z%7D%7BF%7D),


    - shear flow in open profile
    
    ![](http://latex.codecogs.com/png.latex?q%3D%5Cfrac%7B%7BQ%7D_yJ_y-Q_xJ_%7Bxy%7D%7D%7BJ_xJ_y-J_%7Bxy%7D%5E2%7DS_x%20&plus;%20%5Cfrac%7B%7BQ%7D_xJ_x-Q_yJ_%7Bxy%7D%7D%7BJ_xJ_y-J_%7Bxy%7D%5E2%7DS_y).


    - shear flow in close profile wuth three cells
    
    ![](http://latex.codecogs.com/png.latex?%5Cdelta_%7B11%7Dq_1&plus;%5Cdelta_%7B12%7Dq_2&plus;%5CDelta_%7B1p%7D%3D%5COmega_%7B%5CRmnum%7B1%7D%7D%5Cphi%20%5C%5C%20%5Cdelta_%7B21%7Dq_1&plus;%5Cdelta_%7B22%7Dq_2&plus;%5Cdelta_%7B23%7Dq_3&plus;%5CDelta_%7B2p%7D%3D%5COmega_%7B%5CRmnum%7B2%7D%7D%5Cphi%20%5C%5C%20%5Cdelta_%7B32%7Dq_2&plus;%5Cdelta_%7B33%7Dq_3&plus;%5CDelta_%7B3p%7D%3D%5COmega_%7B%5CRmnum%7B3%7D%7D%5Cphi%20%5C%5C%20%5COmega_%7B%5CRmnum%7B1%7D%7Dq_1&plus;%5COmega_%7B%5CRmnum%7B2%7D%7Dq_2&plus;%5COmega_%7B%5CRmnum%7B3%7D%7Dq_3&plus;%5Coint_%7B%5CRmnum%7B1%7D-%5CRmnum%7B2%7D-%5CRmnum%7B3%7D%7D%5Coverline%7Bq%7D%5Crho%20ds%20%3D%20Q_y%20x)


## Examples
<img src="fig/dao-C.png" data-canonical-src="fig/dao-C.png" />
<img src="fig/[]2.png" data-canonical-src="fig/[]2.png" />
<img src="fig/fuselage.png" data-canonical-src="fig/fuselage.png" />

## The order of profile nodes
The Sx and Sy should calculate from the free edge of the profile, when the profile is a close one, you should choose a cut point and the order of profile nodes is very important during calculation.

*****************************************************
### Running requirements
    Python3
    Numpy
    Scipy
    Sympy
    matplotlib

### Installation         
>Copy the source files in the local directory and add the PATH in the system or copy the files to the Python's "site-packages" folder.  
>Copy the source file in you own file and develop the new function by yourself.


*****************************************************

#### Debugs log

- [x] 



