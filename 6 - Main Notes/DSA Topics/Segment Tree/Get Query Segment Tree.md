📌 Created class Segment Tree with **Get query** method

```cpp
class SegmentTree {
public:
	vector<int> segment;
	SegmentTree(int n) {
		segment = vector<int>(n * 4); //4 to be safe side, so that child's child does not give runtime error
	}
	int getQuery(int i, int l, int r, int qL, int qR) { //ql .... qR range, return sum, prod etc
		//1. No overlap
		if(l > qR || r < qL) return 0;

		//2. Total overlap
		if(l >= qL && r <= qR) return segment[i];
	

		//3. Partial overlap, check children
		int mid = (l+r)/2;
		int lc = 2*i+1, rc = 2*i+2;
		
		int leftSum  = getQuery(lc, l,   mid, index, val);
		int rightSum = getQuery(rc, mid+1, r, index, val);

		return leftSum + rightSum; //left and right subtree sum
	}
}
```