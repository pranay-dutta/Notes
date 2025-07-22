**Topic:** [[Matrix]]
**Problem:**  [[Maximum Area of a Piece of Cake After Horizontal and Vertical Cuts]]
**Last Modified:**  `2025-07-23 01:01`

#addhandwrittennote 

 $TC: O(h * w)$  > *descriptive:* $O(n \log n) + O(m \log m) + O(h * w)$
 $SC: O(1)$ >*no auxiliary space*

---
##### **Intuition**: sort and get the max diff Height and max diff Width that will be your answer

`since the answer can be large return mod 1e9+7`
 
```cpp
int maxArea(int h, int w, vector<int>& hCuts, vector<int>& vCuts) {
	sort(begin(hCuts), end(hCuts));
	sort(begin(vCuts), end(vCuts));
	
	int n = hCuts.size(), m = vCuts.size();
	int maxHeight = max(hCuts[0], h-hCuts[n-1]);

	for(int i = 1; i < n; i++) {
		maxHeight = max(maxHeight, hCuts[i]-hCuts[i-1]);
	}

	int maxWidth = max(vCuts[0], w-vCuts[m-1]);
	for(int i = 1; i < m; i++) {
		maxWidth = max(maxWidth, vCuts[i]-vCuts[i-1]);
	}

	long long ans = 1LL * maxHeight * maxWidth;
	int mod = 1e9+7;
	return (int)ans % mod;
}
```

