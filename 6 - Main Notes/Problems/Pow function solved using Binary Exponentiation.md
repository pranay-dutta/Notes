**Topic:** [[Recursion]]
**Problem:**  [[Pow(x, n)]]
**Last Modified:**  `2025-07-04 22:32`

 $TC: O(log (n))$
 $SC: O(log(n))$

---
##### **Intuition**: Binary Exponentiation

😍 Know how [[Binary Exponentiation]] work
 
```cpp
//Binary Exponentiation
double solve(double x, long n) {
	if(n == 0) return 1; //base case
	
	//negative power
	if(n < 0) return 1/solve(x, -n); //solve(2, -2) = 1/solve(2, -(-2))

	if(n&1) return x*solve(x*x, (n-1)/2);
	return solve(x*x, n/2);
}
double myPow(double x, int n) {
	return solve(x, long(n));
}
```
