# SurfsUp Analysis

The purpose if this project is to analysis temperature data for two months of June and December in Oahu.

Weather data is stored at SQLite database in this project. It is a flat file. It means; it is stored locally, which will help us move more quickly through the analysis. SQLAlchemy is a tool that use to query a SQLite database,

First of all the below dependencies are imported in this project:

	Numpy; to make list
	pandas to make DataFrame
	sqlalchemy and its library to access to SQLite database

and then, in first part of this project, the below functions are used to prepare our SQLite file:
	
	 - create_engine: to import our database address to SQLite
	 - automap_base: to set up a foundation to build our schema
	 - prepare: to reflect our tables/ reflect our schema
	 - session: to query our database

## Filter data based on months
In this project we need to analysis two month data; June & December.
Base on our project request; we need to have date and temperature in June. The below code is used

	 - results = session.query(Measurement.date, Measurement.tobs).filter(extract('month', Measurement.date)==6).all()

first part of this code shows that the columns of database and the second part helps us to filter our data based on month. For analyzing data of December, we up 12 instead of 6 in the code as well.

## Results

1700 number of temperatures are submitted in June and 1517 number of temperatures are submitted in December.

The maximum temperature is 85 in June and it is 83 in December. The minimum temperature is 64 in June and it is 56 in December. It shows that maximum temperature in June and December are closed to each other, however, the minimum temperature is not.

The average of temperature in June is about 75 and in December it is 71.

Std for both months are more than 2, (June: std = 3.25 & December: std= 3.74), because it is an academic project, we can accept it but in real world std should be less than 2 for analysis.

Moreover, based on Q1, Q2 & Q3 data in June and December; 75% of temperatures are 77 and 74 respectively.

## Additional query:

Most active station in June & December:

In June we have 3 most active stations with 236 No. temperatures observations (USC00519397/USC00519281/USC00513117). In December the most active station is USC00519281 with highest temperature observations. As a result, we can consider station USC00519281 as the most active station in both months.

It is reported minimum temperature in June and December is 65 & 58 respectively, the maximum ones is 82 & 79 as well as the average temperatures are 73 & 69.
