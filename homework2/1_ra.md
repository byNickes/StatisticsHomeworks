**Made by Nicolò Baroncini (1834907)**

## Research about application (1_RA)
### Understand how the floating point representation works and describe systematically (possibly using categories) all the possible problems that can happen. Try to classify the various issues and limitations (representation, comparison, rounding, propagation, approximation, loss of significance, cancellation, etc.) and provide simple examples for each of the categories you have identified.

#### How does it work?
Mostly used floating point standard is IEEE754. A real number is represented by a couple of values: \
```
(m, e)
```
Where: \
***1-*** m: mantissa \
***2-*** e: exponent \
To get the real number by this couple is used the following formula: 
```
n = m*2ᵉ 
```
The bit representation of floating numbers in IEEE754 standard is as following:
![Single-Precision-IEEE-754-Floating-Point-Standard](https://user-images.githubusercontent.com/78324346/135763086-01f79db7-b86b-489c-9d6c-614fab795b82.jpg) \
As it's possible to see, in this standard also a sign bit is available: if it is 1 then the number is negative, otherwise positive.\
Special number values have a specific representation:\
***1-*** Zero is encoded with both exponent and mantissa as zero \
***2-*** Infinity is represented as all ones in the exponent bits and all zeros in mantissa \
***3-*** Not a Number (NaN) is represented using an all ones exponent and a non-zero mantissa

#### Problems of floating point numbers
We are trying to represent an infinite set of numbers using a finite numbers of bits. This brings errors that need to be accounted for when programming, since they will bring some, apparently, questionable errors.

##### 1. Rounding errors
As said, we have a limited number of digits to represent all real numbers, this brings some inaccuracy. When there are more digits needed to represent a real number than the format allows, the leftover ones are omitted, this means that the number is rounded.\
Let's see an example of this error with a floating point standard that has the mantissa made by 3 bits. In this case, if we have two real numbers with mantissa 1000 and 1001, they will be both represented by a 100 mantissa, so, if the exponent is equal between the two they will figure as equal. \
From this example is possible to understand that bigger the real number, bigger the interval between a real number and another. That is because if we have 3 bits mantissa allowed and 5 bits for the mantissa of the number that I have to represent then I'll have that from 10000 and 10011 they will look the same since bit 0 and bit 1 will be rounded.

##### 2. Comparison errors
This error is related to a rounding error. It could happen that two different real numbers are seen equal by the computer.
For example this instruction
```
1.999999999999999999999>=2
```
will return true because of the rounding of the mantissa.

##### 3. Propagation errors
These errors are made when computing real numbers. For example if we have 100000 as mantissa which is made by 6 digits and we want to add 1 to it we will extend the mantissa to the length of registers, usually 32 or 64 bits. This means that we will have 100000 as first 6 most significant bits and then everything will be 0. If we add 1 to position 0 then we will never see any difference in floating point representantion, even if we add 1 to the mantissa forever. 

##### 4. Loss of significance errors
This kind of error is possible to be seen easily with decimal numbers. \
Imagine to have two real numbers: \
```
x = 0.1234567891234567890 
y = 0.1234567890 
```
Then computing the subtraction x - y will give us 0.0000000001 as result since we can only represent 10 decimal digits. This means that we lost the information that shows that x and y are distant more than 0.0000000001.

*References:* \
[1] [https://www.geeksforgeeks.org/ieee-standard-754-floating-point-numbers/](https://www.geeksforgeeks.org/ieee-standard-754-floating-point-numbers/) \
[2] [https://en.wikipedia.org/wiki/Floating-point_arithmetic](https://en.wikipedia.org/wiki/Floating-point_arithmetic) \
[3] [https://docs.oracle.com/cd/E19957-01/806-3568/ncg_math.html](https://docs.oracle.com/cd/E19957-01/806-3568/ncg_math.html) \
[4] [https://en.wikipedia.org/wiki/Loss_of_significance](https://en.wikipedia.org/wiki/Loss_of_significance) 
