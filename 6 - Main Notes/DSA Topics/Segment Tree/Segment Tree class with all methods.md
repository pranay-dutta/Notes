1. **build** method is used to build the segment tree
2. **getQuery** method is used to get a range 
3. **updateQuery** method is used to update a specific value of an index

```cpp
class SegmentTree {
public:
	vector<int> segment;
	SegmentTree(int n) {
		segment = vector<int>(n * 4); //4 to be safe side, so that child's child does not give runtime error
	}

	//1. Build method used to fill the values in segment tree
	void build(vector<int>& nums, int i,  int l, int r) { //TC: O(nums.size())
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
	
	//2. getQuery method used to get the [sum, max, etc] within a range
	int getQuery(int i, int l, int r, int qL, int qR) { //TC: O(log (n)) //ql .... qR range, return sum, prod etc
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

	//3. updateQuery methods is used to update a value at a specific index and 
	//then bactrack to update the segment tree inner nodes
	void updateQuery(int i, int l, int r, int index, int val) { //TC: O(log (n))
		if(index < l || index > r) return; //invalid index
		
		if(l==r) {
			segment[i] = val; 
			return;
		}
		
		int mid = (l+r)/2;
		int lc = 2*i+1, rc = 2*i+2;
		
		if(index <= mid) { //agar index <= mid he. To left jao
			updateQuery(lc, l, mid, index, val);
		} else { //wrna right jao
			updateQuery(rc, mid+1, r, index, val);
		}
		
		//Backtrack and update internal nodes since leaf is changed
		segment[i] = mid(segment[lc], segment[rc]); //used max here but [min, prod, sum, avg] is also valid for other usecases
	}

}


```