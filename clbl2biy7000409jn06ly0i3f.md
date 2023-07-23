---
title: "Time & Space Complexity of Sieve of Eratosthenes"
seoTitle: "Sieve of Eratosthenes Time and Space Complexity"
seoDescription: "here we are going to evaluate the time and space complexity of SoE. In the simplest and in-depth understanding"
datePublished: Mon Dec 12 2022 17:22:18 GMT+0000 (Coordinated Universal Time)
cuid: clbl2biy7000409jn06ly0i3f
slug: time-space-complexity-of-sieve-of-eratosthenes
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1670865485433/iAmE_WVLk.png
tags: time-complexity, sieve-of-eratosthenes, dsawithkunal, wemakedevs, eddiehub

---

In the previous article, we learned about what is sieve of Eratosthenes algorithm and how to implement it in java.

in this article, we are going to learn about the time and space complexity of sieve of the Eratosthenes algorithm.

Let us take an **example when n = 50**. So we need to print all prime numbers smaller than or equal to 50.

We create a table of all numbers from 2 to 50.

It involves methodically eliminating the numbers known not to be prime until only the prime numbers remain. Begin by **crossing out 1 as it is not a prime number** (it does not have two factors, it is a square number).

**2 is a prime number but all of its multiples a not (they are composite numbers) so cross out all of the multiples of 2 but leave 2 as the first prime number**.

Next, cross out all of the multiples of 3 except 3 itself.

The number 4 and all of its multiples have already been crossed out as they are also multiples of 2.

Next, cross out all the multiples of 5 except 5 itself.

Continue this process until you have discovered as many prime numbers as you need.

at first, we are eliminating all the numbers that are multiples of 2 and how many numbers multiple of 2 exist in the range till n ---&gt; n/2

same goes for 3:--

we are eliminating all the numbers that are multiples of 3 and how many numbers multiple of 3 exist in the range till n ---&gt; n/3

same for 5, 7 ......

the first time the loop is running for 2, now mark all the multiple of 2 as not prime. ok

same for 3, 5, 7 ......

## So, Time Complexity:-

n/2 + n/3 + n/5 + n/7 + ..........

taking n common

n(1/2 + 1/3 + 1/5 + 1/7 + .........)

so the expression\_\_

(1/2 + 1/3 + 1/5 + 1/7 + .........)

1.  **Proof of Harmonic Progression of the sum of primes:** In order to understand the proof, the prerequisite is the **harmonic serise** and **Taylor series expansion**.
    
    *   Lets take an the equation: 
        
        ![log(\frac{x}{1 - x})](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-fc698314a94bb8e35aa8ac4eafb4325f_l3.svg align="center")
        
    *   The taylor series expansion of the above equation is given by: 
        
        ![x + \frac{x^2}{2} + \frac{x^3}{3} + ...](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-130317daca9809275aa34c00937f9490_l3.svg align="center")
        
    *   Putting **x = 1** in the above equation, we get the relation: 
        
        ![\sum_1^n \frac{1}{r} = log(n) ](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-8e1f1194eef7026c5d7f7d2d16c942b4_l3.svg align="center")
        
         Let’s mark the above equation as **1**.
        
    *   From **Euler’s product formula**, 
        
        ![\sum_1^\infty \frac{1}{r^{s}} = \prod \frac{1}{1 - p^{-s}}](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-bdf6aa8fda301a6df32f066267cb4fb2_l3.svg align="center")
        
    *   On substituting **s = 1** in the above equation, we get 
        
        ![\sum_1^\infty \frac{1}{r^{1}} = \prod \frac{1}{1 - p^{-1}}](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-1418dae9f529eaa9bf280cd488632cab_l3.svg align="center")
        
    *   On applying **log** to both the sides: 
        
        ![log(\sum_1^\infty \frac{1}{r^{1}}) = log(\prod \frac{1}{1 - p^{-1}})](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-afe88bf2558808f207d490c53b40e91a_l3.svg align="center")
        
    *   On **simplifying** the above equation, it becomes: 
        
        ![log(\sum_1^\infty \frac{1}{r^{1}}) = \sum log( \frac{1}{1 - p^{-1}})](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-ee4fa2a994213f3299db8e333dfa7232_l3.svg align="center")
        
    *   In the above equation, **1 &gt; p<sup>-1</sup> &gt; -1**
        
    *   Thus, we can use taylor series expansion for the right hand side of the above equation. 
        
        ![log( \frac{1}{1-x}) = \sum_1^\infty log( \frac{1}{n * p^{n}})](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-c8980dd6a0649533bff6a5bdf309e42b_l3.svg align="center")
        
    *   On substituting this in the above equation, we get: 
        
        ![log( \sum_1^n \frac{1}{r}) = \sum \sum_1^n  \frac{1}{n * p^{n}} ](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-c971e73f871c3618c13b63329f2e8141_l3.svg align="center")
        
         where p is a prime number.
        
    *   On expanding the inner summation; 
        
        ![\sum_1^n \frac{1}{n * p^{n}} =  \frac{1}{p} + \frac{1}{2p^{2}} + \frac{1}{3p^{2}} + .....](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-93341247dedc99e807481391b575a05b_l3.svg align="center")
        
    *   The above series is convergent. So, the above series can be approximated to: 
        
        ![\frac{1}{p}](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-15130de644e875d341c9e160938bce90_l3.svg align="center")
        
    *   Therefore, on substituting and rewriting the equation; we get 
        
        ![log( \sum_1^\infty \frac{1}{n}) = \sum \frac{1}{p} ](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-293bfaeb6a1cfdc3639d716f374e632c_l3.svg align="center")
        
         where p is the prime number.
        
    *   **From the initial equation 1, we can finally conclude that:** 
        
        ![\sum \frac{1}{p} = log(log(n)) ](https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-4af2481547e38d3c9ecfcc95a8550f01_l3.svg align="center")
        
          **where p is the sum of prime numbers.** 
        

so now the total **time complexity is O(n\*log(log(n)))**

## Space Complexity:-

the space complexity of sieve of Eratosthenes is equal to the range of number.

means if we want to list all the prime numbers between 1 to n then **time complexity is O(N)**