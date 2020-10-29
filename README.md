# Vehicle-Occupant Databases of Frontal Motor Vehicle Crashes

Bingbing Nie, Qingfan Wang, Iason Bance.

Automobile Crash Lab, Tsinghua University.



## Description

Road traffic accidents remain a worldwide public health concern. Accurate prediction of occupant injury severity in unavoidable collision scenarios is a prerequisite for enhancing road traffic safety with the development of highly automated vehicles. Specifically, a safety prediction model provides a decision reference for the trajectory planning system in the pre-crash phase, and an  adaptive restraint system in the in-crash phase. 

Here we provide two vehicle-occupant databases of frontal motor vehicle crashes that can be used for training and testing occupant injury severity prediction models: 28000-case numerical database and 192-case real-world database.

The two vehicle-occupant databases can be downloaded from:

Google disk: https://drive.google.com/drive/folders/1IPCXin1PDf8pJ2WbBMfPgT78MxZ8uxRU?usp=sharing.



### 28000-case Numerical Database

By combining existing finite element (FE), multi-body (MB), and lumped parameter model (LPM) numerical solvers for motor vehicle crash and occupant injury simulation, we generated a large-scale numerical training database to develop a credible prediction model. More details about the generation of the numerical database can be found in this [paper](https://link.springer.com/article/10.1007/s11431-019-1565-9).

In folder `Vehicle Crash Database\numerical_data` you will find eight `npy` files.  Each file represents an input/output variable. *CrashPulse*, *Gender*, *Seatbelt*, and *Airbag* are four input variables that define the initial collision scenario. *HeadAcceleration*, *ChestDisplacement*, *NeckForce*, and *NeckMoment* are four output variables that can be used to calculate injury risk criteria and injury severity measured by the abbreviated injury scale (AIS).

| Variable                           | Shape       | Description                                                  |
| ---------------------------------- | ----------- | ------------------------------------------------------------ |
| CrashPulse [m/s<sup>2</sup>]       | (28000,100) | Acceleration curves measured in the vehicle during collision (0 to 200 ms with an interval of 2 ms) |
| Gender                             | (28000,)    | Occupant gender (scalar); 1 for female and 0 for male        |
| Seatbelt                           | (28000,)    | use of seatbelt (scalar); 1 for w/ seatbelt and 0 for w/o seatbelt |
| Airbag                             | (28000,)    | use of airbag (scalar); 1 for w/ airbag and 0 for w/o airbag |
| HeadAcceleration [m/s<sup>2</sup>] | (28000,100) | Occupant head acceleration curves during collision (0 to 200 ms with an interval of 2 ms) |
| ChestDisplacement [m]              | (28000,100) | Occupant chest displacement curves during collision (0 to 200 ms with an interval of 2 ms) |
| NeckForce [N]                      | (28000,100) | Occupant neck force curves during collision (0 to 200 ms with an interval of 2 ms) |
| NeckMoment [Nm]                    | (28000,100) | Occupant neck moment curves during collision (0 to 200 ms with an interval of 2 ms) |

Given below are the ratios of cases with different AIS levels in the numerical database, and distributions of occupant gender, airbag usage, and belt usage in cases with the same AIS level: (a) head; (b) neck; (c) chest.

![pie](https://github.com/wangqf1997/Vehicle-Crash-Database/blob/main/pie.png)



### 192-case Real-world Database

In folder `Vehicle Crash Database\realworld_data` you will find 192 `xml` files. Each file represents a vehicle crash case and contains the most comprehensive crash information.

The vehicle crash cases in the real-world database was screened  from 2004 to 2015 from the National Automotive Sampling System/Crashworthiness Data System ([NASS/CDS](https://crashviewer.nhtsa.dot.gov/LegacyCDS/Search)). We excluded crash cases that lacked the necessary elements including collision delta-v, impact angle, occupant gender, use of seatbelts and airbags, and cases with vehicle body types differing from the sedan model.

Finally, the dataset contained 192 frontal collision cases with occupant injury AIS levels for the head, neck, and chest ranging from 0 to 6, delta-v ranging from 35 km/h to 65 km/h, and impact angles ranging from -20° to 10° for frontal collisions.



## Suggestion

We suggest you train your deep-learning model in the large-scale numerical database to get the best prediction performance, and evaluate the model in the real-world database to test its generalization ability.



## Citation

```
@ARTICLE{Bance_2020, 
author={I. {Bance} and S. {Yang} and Q. {Zhou} and S. {Li} and B. {Nie}}, 
journal={Science China Technological Sciences}, 
title={A framework for rapid on-board deterministic estimation of occupant injury risk in motor vehicle crashes with quantitative uncertainty evaluation}, 
year={2020}, 
}
```

If you find the numerical database is useful, please cite the above paper.



## Terms of use

The databases are licensed under a [Creative Commons Attribution 4.0 License](https://creativecommons.org/licenses/by/4.0/legalcode).



## Contact

Contact Information Email: wqf20@mails.tsinghua.edu.cn.
