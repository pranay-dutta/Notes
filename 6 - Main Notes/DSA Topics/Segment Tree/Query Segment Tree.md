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
	
}
```
