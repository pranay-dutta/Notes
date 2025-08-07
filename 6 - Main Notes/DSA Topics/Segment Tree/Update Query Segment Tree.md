📌 Created class Segment Tree with **query** method

```cpp
class SegmentTree {
private:
	vector<int> segment;
public:
	SegmentTree(int n) {
		segment = vector<int>(n * 4); //4 to be safe side, so that child's child does not give runtime error
	}
	vector<int> getSegment() { return segement; } //getter function to get the segement
	void update(int i, int l, int r, int index, int val) {
		if(index < l || index > r) return; //invalid index
		
		if(l==r) {
			segment[i] = val; 
			return;
		}
		
		int mid = (l+r)/2;
		int lc = 2*i+1, rc = 2*i+2;
		
		if(index <= mid) { //agar index <= mid he. To left jao
			update(lc, l, mid, index, val);
		} else { //wrna right jao
			update(rc, mid+1, r, index, val);
		}
		
		//Backtrack and update internal nodes since leaf is changed
		segment[i] = mid(segment[lc], segment[rc]); //used max here but [min, prod, sum, avg] is also valid for other 
	}
	
}
```
