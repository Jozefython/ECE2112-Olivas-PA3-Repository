# PA3 - PYTHON DATA ANALYSIS (PANDAS)
### KAROL JOZEF S. OLIVAS | 2ECE-C | ECE2112

---

# PRE-CODE
- To ensure everything works beforehand.

```python

import pandas as pd #Import Python Data Analysis for Tables
cars = pd.read_csv('cars.csv') #Assign the variable Cars by reading cars.csv
cars #Print cars
```

---

# 🏎️ PROBLEM 1

• Load the corresponding .csv file into a data frame named cars using pandas. Then Display the first five and last five rows of the resulting cars.

• Before the code starts, ```import pandas as pd``` was used. A file named cars.csv was given alongside the instructions. We use ```pd.read_csv('cars.csv')``` and assign it to the variable ```cars```. We then use ```cars.head()``` and ```cars.tail()``` to print the first five (5) and last five (5) rows. These commands automatically use 5 indexes.

**Code:**

```python
cars.head() #Prints the first 5 rows of the table
cars.tail() #Prints the last 5 rows of the table
```


**Output:**

```python 
#First 5:
Model	mpg	cyl	disp	hp	drat	wt	qsec	vs	am	gear	carb
0	Mazda RX4	21.0	6	160.0	110	3.90	2.620	16.46	0	1	4	4
1	Mazda RX4 Wag	21.0	6	160.0	110	3.90	2.875	17.02	0	1	4	4
2	Datsun 710	22.8	4	108.0	93	3.85	2.320	18.61	1	1	4	1
3	Hornet 4 Drive	21.4	6	258.0	110	3.08	3.215	19.44	1	0	3	1
4	Hornet Sportabout	18.7	8	360.0	175	3.15	3.440	17.02	0	0	3	2


#Last 5:
Model	mpg	cyl	disp	hp	drat	wt	qsec	vs	am	gear	carb
27	Lotus Europa	30.4	4	95.1	113	3.77	1.513	16.9	1	1	5	2
28	Ford Pantera L	15.8	8	351.0	264	4.22	3.170	14.5	0	1	5	4
29	Ferrari Dino	19.7	6	145.0	175	3.62	2.770	15.5	0	1	5	6
30	Maserati Bora	15.0	8	301.0	335	3.54	3.570	14.6	0	1	5	8
31	Volvo 142E	21.4	4	121.0	109	4.11	2.780	18.6	1	1	4	2

```

---

# 🏎️ PROBLEM 2:

• Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7...) of cars. Display the row that contains the ‘Model’ of ‘Mazda RX4’. How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have? Determine how many cylinders (‘cyl’) and what gear types (‘gear’) the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’, and ‘Honda Civic’ have.

• Before the code starts, ```import pandas as pd``` was used. A file named cars.csv was given alongside the instructions. We use ```pd.read_csv('cars.csv')``` and assign it to the variable ```cars```. Using ```cars.iloc[:5, ::2]```, it prints the first five rows with odd-numbered columns by using increments. The line ```cars[cars['Model'] == 'Mazda RX4']``` was used to display the row that contains the ```'Model'``` of ```'Mazda RX4'```. Then ```cars.loc[cars['Model'] == 'Camaro Z28', 'cyl']``` was used to know how many cylinders the car model Camaro Z28 has. And lastly, to determine how many cylinders and what gear types 'Mazda RX4 Wag', 'Ford Pantera L', and 'Honda Civic' have, `isin()` was used to filter the values, printing only the values Model, cyl, and gear.

---

### - Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7...) of cars.

**Code:**

```python

cars = pd.read_csv('cars.csv') # First reads the csv file "cars.csv" then assigns it to the variable cars
cars.iloc[:5, ::2] #locates the first 5 rows, then ::2 takes every 2nd column starting at index 0 so we get odd-numbered columns

cars[cars['Model'] == 'Mazda RX4']

```

**Output:**

```python 
#First 5 rows with odd-numbered columns:
Model	cyl	hp	wt	vs	gear
0	Mazda RX4	6	110	2.620	0	4
1	Mazda RX4 Wag	6	110	2.875	0	4
2	Datsun 710	4	93	2.320	1	4
3	Hornet 4 Drive	6	110	3.215	1	3
4	Hornet Sportabout	8	175	3.440	0	3

```
---
### - Display the row that contains the ‘Model’ of ‘Mazda RX4’.
**Code:**

```python
cars[cars['Model'] == 'Mazda RX4'] #It prints a section of cars with a conditional that the Model has to be Mazda RX4
```
**Output:**
```python

#The row that contains the model of Mazda RX4
Model	mpg	cyl	disp	hp	drat	wt	qsec	vs	am	gear	carb
0	Mazda RX4	21.0	6	160.0	110	3.9	2.62	16.46	0	1	4	4
```
---
### - How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have?
**Code:**
```python
cars.loc[cars['Model'] == 'Camaro Z28', 'cyl'] #It locates a Model that's Camarao Z28 then prints its cyl.
```
**Output:**
```python
#How many cylinders does the car model Camaro Z28 have:
23    8
Name: cyl, dtype: int64
```
---
### - Determine how many cylinders (‘cyl’) and what gear types (‘gear’) the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’, and ‘Honda Civic’ have.
**Code:**
```python
subcar = ['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic'] #Creates a list "subcar" with the values of 'Mazda RX4 Wag', 'Ford Pantera L', and 'Honda Civic'
cars.loc[cars['Model'].isin(subcar), ['Model', 'cyl', 'gear']] #Locates and checks whether Model if the model matches whatever is on the subcar list, then prints its model, cyl, and gear.
```

**Output:**

```python
#The cylinders and gears of the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’, and ‘Honda Civic’ have:
Model	cyl	gear
1	Mazda RX4 Wag	6	4
18	Honda Civic	4	4
28	Ford Pantera L	8	5
```
