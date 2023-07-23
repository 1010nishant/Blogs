---
title: "Euclidean Algorithm in java"
datePublished: Sat Dec 17 2022 21:19:49 GMT+0000 (Coordinated Universal Time)
cuid: clbsg08at000408l91yrmd05z
slug: euclidean-algorithm-in-java
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1671311304317/SPmc3EmV5.png
tags: dsa, kunalkushwaha, dsawithkunal, wemakedevs, eddiehub

---

The Euclidean algorithm is an efficient method for computing the greatest common divisor (GCD) of two numbers. It is named after the ancient Greek mathematician Euclid.

It works by repeatedly applying the following steps:

1.  Divide the larger number by the smaller number.
    
2.  If the remainder is 0, the smaller number is the GCD. If the remainder is not 0, repeat the process with the smaller number and the remainder.
    

Here is a description of the algorithm:

1.  Given two positive integers a and b, if b is equal to 0, then the GCD of a and b is a.
    
2.  If b is not equal to 0, then compute the remainder of the division of a by b, denoted as r. The GCD of a and b is the same as the GCD of b and r.
    
3.  Repeat the process with the new pair of numbers (b, r) until one of the numbers becomes 0.
    

For example, to find the GCD of 60 and 48, we can use the following steps:

1.  Divide 60 by 48 to get a quotient of 1 and a remainder of 12.
    
2.  Divide 48 by 12 to get a quotient of 4 and a remainder of 0.
    
3.  The GCD of 60 and 48 is 12.
    

```java
public class EuclideanAlgo {
    public static void main(String[] args) {
        System.out.println(euclidean(4, 8));
    }
    static int euclidean(int a, int b) {
    if (b == 0) {
        return a;
    }
    int r = a % b;
    return gcd(b, r);
}
}
```

This implementation uses recursion, meaning that the function calls itself with the new pair of numbers (b, r) until one of the numbers becomes 0.

### Recursive behaviour of the euclidean algorithm

the function calls itself with the new pair of numbers (b, r) until one of the numbers becomes 0. This is known as a recursive call.

Recursion is a programming technique in which a function calls itself with a modified version of its arguments. In the case of the Euclidean algorithm, the function is called with the new pair of numbers (b, r) until one of the numbers becomes 0. At this point, the function returns the value of the other number, which is the greatest common divisor (GCD) of the original pair of numbers.

The recursive call in the Euclidean algorithm serves to iterate through the steps of the algorithm until the GCD is found. It allows the function to continually reduce the size of the input until the base case is reached, at which point the function returns the result.

The Euclidean algorithm has many important applications in mathematics, including the computation of least common multiples, the solution of linear Diophantine equations, and the construction of a rational approximation to a real number. It is a simple and efficient method for finding the GCD of two numbers.