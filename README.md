# Battery Data Set
 NASA Prognostics Data Repository

# README.txt
Data Description:<br/>
A set of four Li-ion batteries (# 5, 6, 7 and 18) were run through 3 different operational profiles (charge, discharge and impedance) at room temperature. Charging was carried out in a constant current (CC) mode at 1.5A until the battery voltage reached 4.2V and then continued in a constant voltage (CV) mode until the charge current dropped to 20mA. Discharge was carried out at a constant current (CC) level of 2A until the battery voltage fell to 2.7V, 2.5V, 2.2V and 2.5V for batteries 5 6 7 and 18 respectively. Impedance measurement was carried out through an electrochemical impedance spectroscopy (EIS) frequency sweep from 0.1Hz to 5kHz. Repeated charge and discharge cycles result in accelerated aging of the batteries while impedance measurements provide insight into the internal battery parameters that change as aging progresses. The experiments were stopped when the batteries reached end-of-life (EOL) criteria, which was a 30% fade in rated capacity (from 2Ahr to 1.4Ahr). This dataset can be used for the prediction of both remaining charge (for a given discharge cycle) and remaining useful life (RUL).<br/>
<br/>
Files:<br/>
B0005.mat	Data for Battery #5<br/>
B0006.mat	Data for Battery #6<br/>
B0007.mat	Data for Battery #7<br/>
B0018.mat	Data for Battery #18<br/>

Data Structure:<br/>
cycle:	top level structure array containing the charge, discharge and impedance operations<br/>

	type: 	operation  type, can be charge, discharge or impedance<br/>
	ambient_temperature:	ambient temperature (degree C)<br/>
	time: 	the date and time of the start of the cycle, in MATLAB  date vector format<br/>
	data:	data structure containing the measurements<br/>

    	for charge the fields are:<br/>
		Voltage_measured: 	Battery terminal voltage (Volts) 전압<br/>
		Current_measured:	Battery output current (Amps) 전류<br/>
		Temperature_measured: 	Battery temperature (degree C)<br/>
		Current_charge:		Current measured at charger (Amps)<br/>
		Voltage_charge:		Voltage measured at charger (Volts)<br/>
		Time:			Time vector for the cycle (secs)<br/>
	   for discharge the fields are:<br/>
		Voltage_measured: 	Battery terminal voltage (Volts)<br/>
		Current_measured:	Battery output current (Amps)<br/>
		Temperature_measured: 	Battery temperature (degree C)<br/>
		Current_charge:		Current measured at load (Amps)<br/>
		Voltage_charge:		Voltage measured at load (Volts)<br/>
		Time:			Time vector for the cycle (secs)<br/>
		Capacity:		Battery capacity (Ahr) for discharge till 2.7V <br/>
	   for impedance the fields are:<br/>
		Sense_current:		Current in sense branch (Amps)<br/>
		Battery_current:	Current in battery branch (Amps)<br/>
		Current_ratio:		Ratio of the above currents<br/>
		Battery_impedance:	Battery impedance (Ohms) computed from raw data<br/>
		Rectified_impedance:	Calibrated and smoothed battery impedance (Ohms)<br/>
		Re:			Estimated electrolyte resistance (Ohms)<br/>
		Rct:			Estimated charge transfer resistance (Ohms)<br/>
