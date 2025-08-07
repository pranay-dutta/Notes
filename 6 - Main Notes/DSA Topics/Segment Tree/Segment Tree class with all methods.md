- [[Build method Segment Tree]]
- [[Get Query Segment Tree]]
- [[Update Query Segment Tree]]

```cpp
class SegmentTree {
public:
	vector<int> segment;
	SegmentTree(int n) {
		segment = vector<int>(n * 4); //4 to be safe side, so that child's child does not give runtime error
	}

	//1. Build method used to build the seg
	void build(vector<int>& nums, int i,  int l, int r) {
		if(l==r) {
			segment[i] = nums[l]; //l & r both are same
			return 
		}
		
		int mid = (l+r) / 2;
		int leftChild = 2*i+1, rightChild = 2*i+2;
		
		//Fill the child first 
		build(nums, leftChild, l, mid);
		build(nums, leftChild, l, mid);

		//Backtrack and fill the internal nodes
		segment[i] = max(segment[leftChild], segment[rightChild]); //[max, prod, sum, min, avg, etc]
	}

}


```