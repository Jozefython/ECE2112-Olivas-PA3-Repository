# KAROL JOZEF S. OLIVAS

# 2ECE-C | ECE2112

# Programming Assignment # 3 - PYTHON DATA ANALYSIS (PANDAS)


# 🏎️ PROBLEM 1

• Load the corresponding .csv file into a data frame named cars using pandas. Then Display the first five and last five rows of the resulting cars.

• Before the code starts, ```import numpy as np``` was used. The code contains a user-defined ```function``` (using ```numpy```) that turns the given ```array``` (tasked to use a random array) into a ```normalized array``` using both ```.mean``` and ```.std``` functions. Once the array has been normalized, it is saved as an ```.npy``` file with the name "X_normalized.npy" using the ```np.save``` function.

**Example:**

```python 
Random Array:
[[0.99173285 0.94586906 0.40271957 0.7770973  0.98444146]
 [0.92805852 0.03654955 0.60983028 0.2820101  0.15542751]
 [0.25522071 0.19855947 0.63244462 0.57552388 0.46568373]
 [0.61371711 0.23965573 0.25089251 0.307247   0.84723508]
 [0.30733223 0.69882923 0.36368745 0.52503304 0.85940349]]

Normalized Array:
[[ 1.62545366  1.46393902 -0.44882456  0.86958979  1.59977618]
 [ 1.40121716 -1.73833452  0.28053971 -0.87391689 -1.31969208]
 [-0.9682588  -1.1677979   0.36017869  0.15972576 -0.22708899]
 [ 0.29422764 -1.02307269 -0.98350105 -0.78504223  1.11658807]
 [-0.78474206  0.59395976 -0.58628066 -0.01808355  1.15944054]]

[ NORMALIZED ARRAY IS SAVED AS "X_normalized.npy"]
```


# 🏎️ PROBLEM 2:

• Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7...) of cars. Display the row that contains the ‘Model’ of ‘Mazda RX4’. How many cylinders (‘cyl’) does the car model ‘Camaro Z28’ have? Determine how many cylinders (‘cyl’) and what gear type (‘gear’) do the car models ‘Mazda RX4 Wag’, ‘Ford Pantera L’ and ‘Honda Civic’ have.

• Before the code starts, ```import numpy as np``` was used. The code creates an array using numpy with ```np.arange```, which makes an ```array``` that ranges from 1 to 100. Each value is then squared using the mathematical operator ```**```. After that, a ```while``` loop is used with an ```if``` function that checks whether a square is divisible by 3. This process uses the ```modulus``` function (%); if it sees that it is not divisible by 3, then it ```deletes``` the number from the array. This loop stops after the 100th number has been checked. Once the Array has been filtered, it is saved as an ```.npy``` file with the name "div_by_3.npy" using the ```np.save``` function.

**Example:**

```python 
Array of Squares of First 100 Positive Integers:
[    1     4     9    16    25    36    49    64    81   100   121   144
   169   196   225   256   289   324   361   400   441   484   529   576
   625   676   729   784   841   900   961  1024  1089  1156  1225  1296
  1369  1444  1521  1600  1681  1764  1849  1936  2025  2116  2209  2304
  2401  2500  2601  2704  2809  2916  3025  3136  3249  3364  3481  3600
  3721  3844  3969  4096  4225  4356  4489  4624  4761  4900  5041  5184
  5329  5476  5625  5776  5929  6084  6241  6400  6561  6724  6889  7056
  7225  7396  7569  7744  7921  8100  8281  8464  8649  8836  9025  9216
  9409  9604  9801 10000]

Array of Squares of First 100 Positive Integers showing only numbers that are Divisible by 3:
[   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]


[ ARRAY DIVISIBLE BY 3 IS SAVED AS "div_by_3.npy"]
```
