📌What is **binary exponentiation**

>Binary Exponentiation is an efficient method to compute $x^n$ by using the binary representation of the exponent $n$ 
>Instead of performing $n$ multiplications (which takes $O(n)$ time), it reduces the problem by repeatedly squaring $x$
>and halving $n$, resulting in a time complexity of $O(log (n)).$

>This process continues until $n = 0$, and is efficient due to reducing the exponent by half at each step.

---
**Positive power**

● **when power is even** $x^8$  = $(x*x)^8/2$
● **when power is odd**  $x^9$  = $x * ((x*x)^8/2$ )

Generalized
● **Even** >  $pow(x, n)$ = $pow(x*x, n/2)$
● **Odd** > $pow(x, n)$ = $x * pow(x*x, (n-1)/2)$

---
**Negative power**

$x^-8$ = $1/x^8$ = $(1/x)^8$

<img src="negative power rule.png" width=200 style="border-radius: 10px" />