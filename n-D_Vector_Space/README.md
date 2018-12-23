# *n*-Dimensional Vector Space
### Purpose
The purpose of this work is to create a Haskell module for spaces of *n*-dimensional vectors (where n ≥ 1) whose coordinates are of a Floating type.
### Background
A *vector* is a mathematical entity that has direction and magnitude. A vector can be identified with a point in Euclidean space. A point in 3-dimensional Euclidean space can be represented with *Cartesian coordinates* as a triple (3-tuple) *V = (a, b, c)* of real numbers where *a* is the *x*-coordinate, *b* is the *y*-coordinate, and *c* is the *z*-coordinate of the point, respectively. A point in 3-dimensional Euclidean space could also be represented in other ways such as with *polar coordinates*.
&ensp;&ensp;Suppose *V = (a, b, c)* and *V′ = (a′, b′, c′)*  are two vectors represented by points in 3-dimensional Euclidean space. V is the *zero vector* if *a = b = c = 0*. The *scalar product* of a real number *r* and *V* is the vector (*r∗a, r∗b, r∗c*). The *magnitude* of V is the real number *(a² + b² + c²)¹ᐟ²*. The *sum* of *V* and *V′* is the sum of V and the scalar multiple of *-1* and *V′*. The *distance* between *V* and *V′* is the magnitude of the difference of *V* and *V′*. 
### Implementation Details
1. The file contains the following type definitions and type class definition:
```
newtype Vector2 a = Vector2 (a, a) deriving (Show, Eq)
newtype Vector3 a = Vector3 (a, a, a) deriving (Show, Eq)
newtype Vector4 a = Vector4 (a, a, a, a) deriving (Show, Eq)

class VectorSpace v where
vecZero         :: (Num a) => v a
vecSum          :: (Num a) => v a -> v a -> v a
vecScalarProd   :: (Num a) => a -> v a -> v a
vecMagnitude    :: (Floating a) => v a -> a
vecDifference   :: (Num a) => v a -> v a -> v a
vecDistance     :: (Floating a) => v a -> v a -> a
```
2. The file includes instance statements that define **Vector2**, **Vector3**, and **Vector4** to be instances of the type class **VectorSpace**. 
3. The file includes a function named **vecF** of type *(Floating a, VectorSpace v) => v a -> [v a] -> [a]* such that **vecF x y** equals a list whose i*th* entry is the distance between **x** and the i*th* entry of the list **y**. 
### Testing
A test plan is included in the file for **vecScalarProd**, **vecSum**, **vecMagnitude**, and **vecF**. The test plan includes at least three test cases for each function. 
Each test case has the following form: <br/>
&ensp;&ensp;**Function**: Name of the function being tested.<br/>
&ensp;&ensp;**Test Case Number**: The number of the test case.<br/>
&ensp;&ensp;**Input**: Inputs for the function.<br/>
&ensp;&ensp;**Expected Output**: Expected output for the function.<br/>
&ensp;&ensp;**Actual Output**: Actual output for the function.<br/>
#### Author
Michael Balas

#### License
[GNU General Public License](../LICENSE)

