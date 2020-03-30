1.	Test Data
The attached data represents issues raised in testing of a system that was done by 4 different drivers, in different locations and with different characteristics. The data was not processed and is presented as reported by the drivers. However the drives were evenly distributed on a 24hrs,each country and each road type.
Please answer the following questions:
1. Which driver needs to change the way he characterize issues?
2. Which road type seems to be the most challenging
3. In which country do we have the worst performance?
4. Which illumination has the best results? 


2.	Sensor

Columns 1,2 and 3 represent 3 sensors outputs for a real world measure with a value of 2.47 (col 4) and a possible range of -2 to 6
1. Which is the best sensor in terms of signal quality and why?
2. Which sensor is almost not useful at all and why?
3. What is the standard deviation of each data series?
4. What is the statistical distribution that best describes each sensor output?
5. What is the RMS for each sensor?

Notes: 
1.	One can assume each measure of each sensor is independent of the other measures.

2.	If you are not familiar with any of the terms mentioned in the above questions try to search open sources on the internet.


3.	Parser 
The file parser.log consists of a sensor with the following structure:
0x7E	0x40	0x51	Data (17 bytes)	FCS(CRC)	0x7E
Inside the Data stream the speed is from the 9th bit to the 20th (including). The data is in little endian.
Whenever 7E should have appeared in the data or FCS calculation it was replaced by “7D 5E” and 7D was replaced by “7D 5D”.
FCS is calculated as follows 0XFF -Sum(header and data bytes)%0X100
header and data bytes =all the message w/o  starting and ending 0X7E and FCS.
The speed has a factor of 0.1 between the data and real value( meaning a value of 456 is actually 45.6)

Q:
1.	In one of the measures the speed sensor had a large error. Where?
2.	Find the wrong FCS 
