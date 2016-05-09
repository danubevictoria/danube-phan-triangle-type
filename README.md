# Triangle Type
Danube Phan <br>
danubevictoria@gmail.com

## Synopsis
Given valid lengths of the triangle's three sides as input, this project determines the type of triangle as equilateral, isosceles, or scalene. 

## Solution
Before any type can be determined, we must first determine if the inputs of the three sides could actually make a triangle. <i>validTriangle</i> must first check that exactly 3 non-null integers greater than 0 are passed in. If not, then we appropriately handle any exceptions thrown and print out a useful message to the user what the issue was with the values used.

If the lengths input are considered valid, <i>validTriangle</i> then checks that the 3 sides can pass the Triangle Inequality Theorem. The Triangle Inequality Theorem states that given the sum of the lengths of any two sides of the triangle, the sum is greater than the third. Therefore, the following inequalities must hold true in order to be considered a valid triangle:

> a + b > c <br>
> a + c > b <br>
> b + c > a

Once determined that the lengths input do make a valid triangle, triangleType determines what type it is. For efficiency, triangleType checks whether it is equilateral first as there is only one possible way to be an equilateral triangle, and that is if all sides are equal. 

> a = b <br>
> b = c <br>
> a = c <br>

By the Transitive Property of Equality, if a = b, and b = c, then a = c. Therefore, we can minimize the conditional to only check if a = b and b = c to know that it's equilateral. 

The second conditional is for a scalene because again there is only one possible way to be a scalene triangle, and this is if all three sides are unequal.

> a != b 
> b != c 
> a != c

If it's been determined that the lengths given do make a valid triangle, and the type is not equilateral nor scalene, then it must be isosceles. This again adds to efficiency because an isosceles triangle is one where two sides are equal, but not the third, which could result from more than one possibilities:

> a = b and b != c <br>
> or a = c and a != c <br>
> or b = c and b != a 

If the inputs are invalid, then there is no type to determine and we just return null. If the inputs are valid, but they do not pass the Triangle Inequality Theorem to form a triangle, we return "Not a Triangle".

## Tests