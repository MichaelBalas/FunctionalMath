# Solving Cubic Equations
### Purpose
The purpose of this work is to compute an approximation of a real number solution of a cubic equation with floating point coefficients for any value of *Q³ + R²* (described below). 
### Background
Recall from high school mathematics that a quadratic equation <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?ax%5E2%20&plus;%20bx%20&plus;%20c%20%3D%200%2C) <br />
where *a*, *b*, *c* are real numbers with *a ≠ 0*, has two solutions: <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?x_%7B1%7D%20%3D%20%5Cfrac%7B-b%20&plus;%20%5Csqrt%7Bb%5E2%20-%204ac%7D%7D%7B2a%7D) <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?x_%7B2%7D%20%3D%20%5Cfrac%7B-b%20-%20%5Csqrt%7Bb%5E2%20-%204ac%7D%7D%7B2a%7D) <br />
If *b² - 4ac < 0*, the two solutions are non-real complex numbers; if *b² - 4ac = 0*, the two solutions are real numbers equal to each other; and if *b² - 4ac > 0*, the two solutions are distinct real numbers. 

Less well known is that a cubic equation <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?ax%5E3%20&plus;%20bx%5E2%20&plus;%20cx%20&plus;%20d%20%3D%200%2C) <br />
where *a*, *b*, *c*, *d* are real numbers with *a ≠ 0*, has three solutions: <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?x_%7B1%7D%20%3D%20S%20&plus;%20T%20-%20%5Cfrac%7Bb%7D%7B3a%7D) <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?x_%7B2%7D%20%3D%20-%20%5Cfrac%7BS%20&plus;%20T%7D%7B2%7D%20-%20%5Cfrac%7Bb%7D%7B3a%7D%20&plus;%20%5Cfrac%7Bi%5Csqrt%7B3%7D%7D%7B2%7D%28S%20-%20T%29) <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?x_%7B3%7D%20%3D%20-%20%5Cfrac%7BS%20&plus;%20T%7D%7B2%7D%20-%20%5Cfrac%7Bb%7D%7B3a%7D%20-%20%5Cfrac%7Bi%5Csqrt%7B3%7D%7D%7B2%7D%28S%20-%20T%29) <br />
where: <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?Q%20%3D%20%5Cfrac%7B3ac%20-%20b%5E2%7D%7B9a%5E2%7D) <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?R%20%3D%20%5Cfrac%7B9abc%20-%2027a%5E2d%20-%202b%5E3%7D%7B54a%5E3%7D) <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?S%20%3D%20%5Csqrt%5B3%5D%7BR%20&plus;%20%5Csqrt%7BQ%5E3%20&plus;%20R%5E2%7D%7D) <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?T%20%3D%20%5Csqrt%5B3%5D%7BR%20-%20%5Csqrt%7BQ%5E3%20&plus;%20R%5E2%7D%7D) <br />
*x₁* is always a real number. If *Q³ + R² < 0*, the three solutions are distinct real numbers; if *Q³ + R² = 0*, the three solutions are real numbers and at least two are equal; and if *Q³ + R² > 0*, the three solutions are one real number and two non-real complex numbers.
### Implementation Details
1. The file includes a function named **cubicQ** of type ```Float -> Float -> Float -> Float``` that computes **Q** from **a**, **b**, and **c**. The file also includes a function named **cubicR** of type ```Float -> Float -> Float -> Float -> Float``` that computes **R** from **a**, **b**, **c**, and **d**. 
2. The file includes two functions **cubicComplexS** and **cubicComplexT** of type ```Float -> Float -> Complex``` where ```Complex``` is some type of complex number whose real and imaginary parts are of type ```Float```.
3. The file includes **cubicRealSolution** of type ```Float -> Float -> Float -> Float -> Float```. It produces real number solutions for any value of **Q³ + R²** using complex number arithmetic.

#### Author
Michael Balas

#### License
[GNU General Public License](../LICENSE)
