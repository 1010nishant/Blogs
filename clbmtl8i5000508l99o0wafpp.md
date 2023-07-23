---
title: "Find the Square root of a number without sqrt() in java"
seoTitle: "Find the Square root of a number without sqrt() in java"
seoDescription: "In Java, finding the square root of a number is very easy if we are using the pre-defined method. Java Math class provides sqrt() method to find the square"
datePublished: Tue Dec 13 2022 22:53:27 GMT+0000 (Coordinated Universal Time)
cuid: clbmtl8i5000508l99o0wafpp
slug: find-the-square-root-of-a-number-without-sqrt-in-java
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1670971764388/cC6rlF1dh.png
tags: algorithms, java, dsawithkunal, wemakedevs, eddiehub

---

In Java, finding **the square root of a number** is very easy if we are using the pre-defined method. Java **Math** class provides **sqrt()** method to find the square root of a number. In this section, we will create a **Java program to find the square root of a number without using the sqrt() method.**

## What is Perfect Square?

A perfect square is an integer that is the square of an integer. For example,

**X = 9 = 3 \* 3 = 3^{2}*X*\=9=3∗3=32**

Here, 9 is a perfect square because 99 is the square of 33. On the other hand, 1010 is not a perfect square because it cannot be represented as the square of an integer.

first, we have to think for a number which is a perfect square like n = 36.

Let me propose an algorithm first, and then we’ll break it down one step at a time.

1.  Start from **i=1**, if **i \* i == n**, then i is the square root of n as n is a perfect square.
    
2.  if ***i*∗*i* \&gt; *n*,** it means the square root must lie between **(i-1, I)** let’s call them **(*low*,*high*)**.
    
3.  **Apply binary search in the range (*low*,*high*). Find mid*mid* of (*low*,*high*):**
    
4.  if ***mid*∗*mid*\==*n***, it means we assume that ***mid*** is the square root of *n*.
    
5.  if ***mid∗mid &gt; n****, it means that the assumption we made is incorrect. This implies, the square root of n must be less than mid since any value higher than mid can never satisfy the* ***condition mid*∗*mid*\==*n*.** Hence, we will try to find the square root on the left side of mid by repeating step 3 for **(*low*,*mid*)**.
    
6.  Otherwise,***mid∗mid&lt;n*** *means that our assumption is incorrect. It implies the square root of n must be greater than mid since any value less than mid can never satisfy the condition* ***mid*∗*mid*\==*n*.** Hence, we will try to find the square root on the right side of *mid* by repeating step 3 for **(*mid*,*high***).
    
    ```java
    public class SqureRoot {
        public static void main(String[] args) {
            int n = 40;// number whose square root we have to find
            System.out.println(sqrt(n, p));
        }
        // code for square root find
        static int sqrt(int n, int p) {
            int start = 0;
            int end = n;
    
            int root = 0;
            // binary search logic
            while (start <= end) {
                int mid = start + (end - start) / 2;
                if (mid * mid == n) {
                    root = mid;
                    return root;
                }
                if (mid * mid > n) {
                    end = mid - 1;
                } else {
                    start = mid + 1;
                }
            }
            return root;
        }
    }
    ```
    

but consider a scenario we the number would be a **non-perfect square number like 40.**

for this we have to check the digits in decimal numbers till we want to check.

it seems a little bit tricky but it's not.

we just have to **run this binary search loop for 0.1 and if you want to till 0.01 so on .....**

**code for this:-**

```java
public class SqureRoot {
    public static void main(String[] args) {
        int n = 40;// number whose square root we have to find
        int p = 3;// till how many number in decimal i want it(PRECISION)
        System.out.printf("%.3f", sqrt(n, p));
    }

    // code for square root find
    static double sqrt(int n, int p) {
        int start = 0;
        int end = n;

        double root = 0.0;
        // binary search logic
        while (start <= end) {
            int mid = start + (end - start) / 2;
            if (mid * mid == n) {
                root = mid;
                return root;
            }
            if (mid * mid > n) {
                end = mid - 1;
            } else {
                start = mid + 1;
            }
        }
        double incr = 0.1;
        for (int i = 0; i < p; i++) {
            while (root * root <= n) {
                root += incr;
            }
            root -= incr;
            incr /= 10;
        }

        return root;
    }
}
```

hope, you like this article plz follow my blog for more interesting articles.