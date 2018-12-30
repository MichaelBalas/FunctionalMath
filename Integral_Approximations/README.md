# Integral Approximations
### Purpose
The purpose of this work is to implement a practical higher-order function for approximating definite integrals.
### Background
Using the *trapezoidal rule*, the value of a definite integral  <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?%5Cint_%7Ba%7D%5E%7Bb%7Df%28x%29dx)  <br />
can be approximated by the summation  <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%5Cfrac%7Bf%28x_%7Bi-1%7D%29%20&plus;%20f%28x_i%29%7D%7B2%7D*%5Cfrac%7Bb%20-%20a%7D%7Bn%7D)  <br />
where  <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?a%20%3D%20x_0%20%3C%20x_1%20%3C%20%5Ccdots%20%3C%20x_n%20%3D%20b)  <br />
and *xᵢ - xᵢ₋₁= (b - a)/n* for all *i* with *1 ≤ i ≤ n*. Note that  <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?%5Cfrac%7Bf%28x_%7Bi-1%7D%29%20&plus;%20f%28x_i%29%7D%7B2%7D*%5Cfrac%7Bb%20-%20a%7D%7Bn%7D)  <br />
is the area of a trapezoid that approximates the area under the graph of *f* from *xᵢ₋₁* to *xᵢ*. The approximation becomes more accurate as the parameter *n* increases in value.
### Implementation Details
1. The file contains includes a function **definiteIntegral** of type
``` Double -> Double -> (Double->Double) -> Integer -> Double```
such that 
&ensp;&ensp;**definiteIntegral a b g n**
computes an approximation to the definite integral  <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?%5Cint_%7Ba%7D%5E%7Bb%7Df%28x%29dx)  <br />
using the trapezoidal rule with **n** partitions and using **g** to represent the function *f : R → R*. 
2. The file includes a function **circleArea** of type
``` Double -> Double```
such that **circleArea r** computes the area of a circle of radius **r** using **definiteIntegral**.
### Testing
A test plan is included in the file with at least three test cases for each function.<br />
Each test case has the following form:<br />
&ensp;&ensp;**Function**: Name of the function being tested.<br />
&ensp;&ensp;**Test Case Number**: The number of the test case.<br />
&ensp;&ensp;**Input**: Inputs for the function.<br />
&ensp;&ensp;**Expected Output**: Expected output for the function.<br />
&ensp;&ensp;**Actual Output**: Actual output for the function.<br />
There are also three *QuickCheck* cases for **definiteIntegral**.<br />
Each *QuickCheck* case has the following form:<br />
&ensp;&ensp;**Function**: Name of the function being tested.<br />
&ensp;&ensp;**Property**: Code defining the property to be tested by *QuickCheck*.<br />
&ensp;&ensp;**Actual Test Result**: Pass or Fail.<br />
#### Author
Michael Balas

#### License
[GNU General Public License](../LICENSE)
