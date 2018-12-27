# Polynomial List I/O
### Purpose
The purpose of this work is to expand upon the previous project on polynomial data types and involve I/O as well as list manipulation. It differentiates polynomials inputted by the user.
### Background
A polynomial can be represented by the list of the coefficients in its standard form. That is, if   <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?a_0%20&plus;%20a_1%20*%20x%5E1%20&plus;%20a_2%20*%20x%5E2%20&plus;%20%5Ccdots%20&plus;%20a_m%20*%20x%5Em)  <br />
where *a ≠ 0* is the standard form of a nonzero polynomial *p*, then *p* can be represented by the list  <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?%5Ba_0%2C%20a_1%2C%20...%2C%20a_m%5D.)  <br />
The zero polynomial can be represented by the empty list, []. Polynomials can be processed by manipulating their representations as lists. For example, two polynomials can be added by adding the corresponding components in their representations as lists. 

&ensp;&ensp;We will call a list that represents a polynomial a *polynomial list*. Every list of numbers whose final value is not 0 is a polynomial list.
### Implementation Details
1. The file contains the following algebraic data type definition (from *Arbitrary_Polynomials*):
``` 
data Poly a = X
| Coef a
| Sum (Poly a) (Poly a)
| Prod (Poly a) (Poly a)
deriving Show
```
2. The file includes the functions **polyDeriv** and **polyAsList** from *Arbitrary_Polynomials*. 
3. The file includes a function named **polyParse** of type
``` String -> Poly Integer ```
that takes a string like "1 + 2x + 5x^2" as input and returns the member of the type **Poly Integer** that the string represents as output. 
4. The file includes a function **getPoly** of type
``` FilePath -> IO (Poly Integer) ```
that reads a string like "1 + 2x + 5x^2" from a file and then returns a member of the type **Poly Integer** that the string represents as output.
5. The file includes a function named **polyPrettyPrint** of type
``` Poly Integer -> String ```
that takes a member of the type **Poly Integer** as input and returns a nicely formatted string presentation of it as output.
6. Using **polyPrettyPrint**, the file defines **Poly Integer** as an instance of the type class **Show**. 
7. The file includes a function named **polySimp** of type
``` Poly Integer -> Poly Integer ```
that takes a member **p** of the **Poly Integer** as input and returns a simplified member **q** of **Poly Integer** as output such that **p** and **q** represent the same polynomial function. 
8. The file includes a **getPolyAndDiff** function of type
``` FilePath -> IO String ```
that reads a string like "1 + 2x + 5x^2" from a file and returns a nicely formatted string that represents the derivative in simplified form of the polynomial represented by the input string. 
### Testing
A test plan is included in the file with at least three test cases for each function. There is also one *QuickCheck* case for each of the functions **polyParse**, **polyPrettyPrint**, **polyDeriv** and **polySimp**. <br />
Each test case has the following form:<br />
&ensp;&ensp;**Function**: Name of the function being tested.<br />
&ensp;&ensp;**Test Case Number**: The number of the test case.<br />
&ensp;&ensp;**Input**: Inputs for the function.<br />
&ensp;&ensp;**Expected Output**: Expected output for the function.<br />
&ensp;&ensp;**Actual Output**: Actual output for the function.<br />

#### Author
Michael Balas

#### License
[GNU General Public License](../LICENSE)
