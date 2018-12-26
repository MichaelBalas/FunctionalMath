# Arbitrary Polynomials
### Purpose
The purpose of this work is to create a Haskell module that defines arbitrary algebraic data types of polynomials and implements various functions on the members of the type including symbolic differentiation.
### Background
Let *C* be a set of *coefficients* closed under addition and multiplication such as the integers *Z*, the rational numbers *Q*, or the real numbers *R*. A *polynomial over C* is a mathematical expression that is constructed from an *indeterminant x* and members of *C* by applying addition (+) and multiplication (∗) operators. Let *P* be the set of polynomials over some *C*. The value of a polynomial *p* ∈ *P* at *c* ∈ *C* is the result of replacing the indeterminant *x* with *c*. For example, the value of *(2∗x) + 4* at *3* is *(2∗3) + 4 = 12.*   
&ensp;&ensp;Every polynomial *p* represents a *polynomial function* *fp : C → C* that maps *c* ∈ *C* to the value of *p* at *c*. For every *p* ∈ *P*, there is a *q* ∈ *P* that has the form <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?a_0%20&plus;%20a_1*x%5E1%20&plus;%20a_2*x%5E2%20&plus;%20%5Ccdots%20&plus;%20a_m*x%5Em%2C)  <br />
where *a₀, a₁, ...* ∈ *C*, *xⁱ* is an abbreviation for *x∗...∗x (i times)*, and parentheses have been depressed, such that *fp* and *fq* are the same function. *q* is called the *standard form* of *p*. The *degree* of *p* is *m*, the largest exponent appearing in *q*. For example, the standard form of *(x+1)∗(x+2)* is  <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?2%20&plus;%203%20*%20x%5E1%20&plus;%20x%5E2)  <br />
and the degree of *(x+1)∗(x+2)* is 2.
### Implementation Details
1. The file contains the **algebraic data type definition**
```
data Poly a = X
| Coef a
| Sum (Poly a) (Poly a)
| Prod (Poly a) (Poly a)
deriving Show
```

2. The file includes a function named **polyValue** of type
``` Num a => Poly a -> a -> a```
such that **polyValue p n** is the value of **p** at **n**. 

3. The file includes a function named **polyDegree** of type
``` Poly a -> Integer```
such that **polyDegree p** is the degree of *p*.

4. The file includes a function named **polyDeriv** of type
```Num a => Poly a -> Poly a```
such that **polyDeriv p** represents the derivative of the polynomial function represented by **p**. **polyDerivative p** thus symbolically differentiates a polynomial *p*. 

5. The file includes a function named **polyNewton** of type
``` (Fractional a, Ord a) => Poly a -> a -> a ```
such that **polyNewton p s** computes, using Newton's method with the seed **s**, a number **n** such that **polyValue p n** is approximately 0. **polyNewton p** thus solves the polynomial equation *p = 0*.

6. The file includes a function named **polyAsList** of type
``` (Num a, Eq a) => Poly a -> [a]```
such that **polyDeriv p** returns the list *[a₀, a₁, ..., am]* where  <br />
&ensp;&ensp;![equation](https://latex.codecogs.com/gif.latex?a_0%20&plus;%20a_1*x%5E1%20&plus;%20a_2*x%5E2%20&plus;%20%5Ccdots%20&plus;%20a_m*x%5Em)  <br />
is the standard form of **p**. **polyAsList p** thus transforms a polynomial *p* into standard form. 
### Testing
A test plan is included in the file for **polyValue**, **polyDegree**, **polyDeriv**, **polyNewton** and **polyAsList**. The test plan includes at least three test cases for each function. 
Each test case has the following form:
&ensp;&ensp;**Function**: Name of the function being tested.
&ensp;&ensp;**Test Case Number**: The number of the test case.
&ensp;&ensp;**Input**: Inputs for the function
&ensp;&ensp;**Expected Output**: Expected output for the function.
&ensp;&ensp;**Actual Output**: Actual output for the function.
#### Author
Michael Balas

#### License
[GNU General Public License](../LICENSE)
