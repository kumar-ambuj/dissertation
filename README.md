<center> <img  src = "https://www.bits-pilani.ac.in/Uploads/Campus/BITS_university_logo.gif" style="width:50%" ></center>

<h1><center>Work Integrated Learning Programmes Division<br>
M.Tech (Data Science and Engineering)<br> I SEMESTER 21-22
 DISSERTATION (DSECLZG628T)<br>
</center></h1>

| |||
| ----------- | ----------- |---------------|
| Submitted By      | AMBUJ KUMAR       |2019HC04622|
| Evaluation By    | Ms. C V KRISHNAVENI         |krishnaveni@wilp.bits-pilani.ac.in|

## Title
A study of ML/DL based Remaining Useful Life Prediction of
Lithium-ion Battery for preventive maintenance

### Introduction
At present time, we are heavily dependent on machines, devices and equipment in our day-to-day life. Many of these systems have an energy storage device, battery as their integral part. Various batteries are used in these systems, but Lithium-ion batteries are emerged as one of the best performing option because of its high charge density, portability and long life span. These machines are meant to falter after the continuous use over a period. To ensure the smooth functioning of battery-based equipment, maintenance is performed. It is essential to monitor the health of batteries to ensure the proper functioning of these systems. There are different maintenance programs like reactive maintenance, preventive maintenance and predictive maintenance which are adopted for these systems. 

However, battery degradation begins immediately after batteries are manufactured, and when 70% or 80% of initial capacity remains, batteries need be replaced for safe operation. Thus, it is important to predict when battery life will be over. 

Reactive maintenance is performed when equipment stops working. It is the traditional way which may leads to downtime period and there is always an uncertainty about the current health of the equipment. 

In the preventive maintenance, periodic maintenance is scheduled to ensure that machine does not brake while in operation. In this process the selection of maintenance period is of utmost importance otherwise it may result into over maintenance or under maintenance. These both scenarios are risky and possess substantial time and economic loss. 

In predictive maintenance one collects the data regarding the health of the equipment in terms of various sensors and operational data, then accordingly maintenance of the device can be scheduled. This method is cost effective, and it reduces the chances of downtime. Predictive maintenance in batteries is used for their health monitoring, which includes prediction of battery’s Remaining Useful Life.

This dissertation project investigates how to make use of Deep Learning based mechanism to solve the prediction of battery’s RUL by programming.

### Loading & processing dataset into memory
First thing is to convert MATLAB file into dataframe/json file so that it can be opened in Python. 

As per the README of the dataset, the data is stored in several ".mat" files, each file corresponds to a specific battery and the data structure of each file is as follows:

<B>Data Description:</B><br>
A set of four Li-ion batteries (# 5, 6, 7 and 18) were run through 3 different operational profiles (charge, discharge and impedance) at room temperature. Charging was carried out in a constant current (CC) mode at 1.5A until the battery voltage reached 4.2V and then continued in a constant voltage (CV) mode until the charge current dropped to 20mA. Discharge was carried out at a constant current (CC) level of 2A until the battery voltage fell to 2.7V, 2.5V, 2.2V and 2.5V for batteries 5 6 7 and 18 respectively. Impedance measurement was carried out through an electrochemical impedance spectroscopy (EIS) frequency sweep from 0.1Hz to 5kHz. Repeated charge and discharge cycles result in accelerated aging of the batteries while impedance measurements provide insight into the internal battery parameters that change as aging progresses. The experiments were stopped when the batteries reached end-of-life (EOL) criteria, which was a 30% fade in rated capacity (from 2Ahr to 1.4Ahr). This dataset can be used for the prediction of both remaining charge (for a given discharge cycle) and remaining useful life (RUL).

Files:<br>
B0005.mat	Data for Battery #5<br>
B0006.mat	Data for Battery #6<br>
B0007.mat	Data for Battery #7<br>
B0018.mat	Data for Battery #18<br>

For the proposed Deep Learning model, it is only necessary to collect the data related to the discharge of the battery. To pre-process the data in .mat format, a function is created in Python and storing it in memory in two pandas DataFrame for later access. After loading the dataset, a description of the data is made using panda functions to verify if the data loading was correct.
Another python function is created to process the three different types of data – charge, discharge and impedance for different visualization of data.
