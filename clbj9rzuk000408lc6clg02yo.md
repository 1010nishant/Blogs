---
title: "Sieve Of Eratosthenes Algorithm in java"
seoTitle: "Sieve Of Eratosthenes Algorithm in java"
seoDescription: "find prime numbers 1 to n using Sieve Of Eratosthenes Algorithm in java. time complexity of this algorithm"
datePublished: Sun Dec 11 2022 11:15:31 GMT+0000 (Coordinated Universal Time)
cuid: clbj9rzuk000408lc6clg02yo
slug: sieve-of-eratosthenes-algorithm-in-java
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1670757188736/J7aQ5KWZU.png
tags: algorithms, dsa, sieve-of-eratosthenes, wemakedevs, eddiehub

---

first, we are going to understand the conceptual part of this algorithm after that we will be looking for the coding region of the sieve of Eratosthenes, ok.

***great, first of all, we should have the question why use this algorithm?***

here is the answer, The sieve of Eratosthenes is one of the most efficient ways to find all primes smaller than n when n is smaller than 10 million. the **Time Complexity** of this algorithm is **O(n\*log(log(n)))** and **Auxiliary Space: O(n).**

if you want to learn how to evaluate the time and space complexity of the sieve of Eratosthenes check out my next article.

### Explanation of algorithm using an example:

Let us take an example when n = 50. So we need to print all prime numbers smaller than or equal to 50.

We create a table of all numbers from 2 to 50.

It involves methodically eliminating the numbers known not to be prime until only the prime numbers remain. Begin by crossing out one as it is not a prime number (it does not have two factors, it is a square number). Two is a prime number but all of its multiples a not (they are composite numbers) so cross out all of the multiples of two but leave two as the first prime number. Next, cross out all of the multiples of three except three itself. The number four and all of its multiples have already been crossed out as they are also multiples of two. Next, cross out all the multiples of five except five itself. Continue this process until you have discovered as many prime numbers as you need.

first, we start from 2(prime number so mark as blue) then we mark all the multiple of 2 as red means red ones are eliminated.

our table should look like this:-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670756247081/q4PzR0qbx.png align="center")

after this, we are going to do this same procedure for number 3

our table should look like this:-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670756345090/qq-8Js3HA.png align="center")

doing the same for 5 and for 7, the table should look like this:-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670756397498/DYm-w5DXY.png align="center")

in the end, repeating this procedure again and again the table should look like this:-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1670756538495/VvCokw9GC.png align="center")

all the blue one is prime and all the red one is not prime.

that's how we perform the sieve of Eratosthenes algorithm.

here is the code for it:-

```java
public class SieveofEratosthenes {
    public static void main(String[] args) {
        int n = 100;
        boolean[] primes = new boolean[n + 1];// by default value is false in bool array
        sieve(n, primes);
    }
    // false in array means number is prime
    private static void sieve(int n, boolean[] primes) {
        for (int i = 2; i * i <= n; i++) {
            if (!primes[i]) {
                for (int j = i * 2; j <= n; j += i) {
                    primes[j] = true;
                }
            }
        }
        for (int i = 2; i <= n; i++) {
            if (!primes[i]) {
                System.out.println(i + " ");
            }
        }
    }
}
```