```run-js
const arr = [2, "3", { name: "John" }, [1, 2, 3], true, null];

console.log(arr.at(0)); // 2
console.log(arr.at(-1)) // null
console.log(arr.concat([2])) // [2, "3", { name: "John" }, [1, 2, 3], true, null, 2]
console.log(arr.includes(2)); // true
console.log(arr.indexOf("3")); // 1
console.log(arr.push(4)) // [2, "3", { name: "John" }, [1, 2, 3], true, null, 4]
console.log(arr.pop()); // 4
console.log(arr.shift()) //Original array is modified 
console.log(arr.unshift(1)) // [1, "3", { name: "John" }, [1, 2, 3], true, null]
console.log(arr.slice(1, 5)); // returns a sliced piece. ["3", { name: "John" }] // Original array is not modified

console.log(arr.splice(1, 4)); // return (s, number of elements) ["3", { name: "John" }] // Original array is modified

const nums = [2, 4, 1, 6, 7];
console.log(nums.sort((a, b) => b - a)); // [1, 2, "3", true, null, { name: "John" }] // Original array is modified
console.log(arr.reverse()); // [null, true, [1, 2, 3], { name: "John" }, "3", 2] // Original array is modified

const cp = [2, 4, 1, 6, 7];
//Copy from index 2 and paste it at index 0 
console.log(cp.copyWithin(0, 2));  //copies [1,6,7] and pastes it at index 0

console.log(nums.every(n => n > 0)) //every element is greater than 0 in nums
console.log(nums.some(n => n > 12)) //no element is greater than 12 in nums
console.log(nums.filter(n => n > 2)) // [4, 6, 7] // Original array is not modified
console.log(nums.find(n => n == 7)); // 7 // Original array is not modified
console.log(nums.findIndex(n => n == 7)); // 4 // Original array is not modified
console.log(nums.forEach(n => console.log(n * 2))) // prints each element multiplied by 3
console.log(nums.map(n => n * 2)); // [4, 8, 2, 12, 14] // Original array is not modified
console.log(nums.reduce((acc, n) => acc + n, 0)); // 20 // Original array is not modified
console.log(nums.reduceRight((acc, n) => acc + n, 0)); // 20 // Original array is not modified
console.log(nums.toString()); // "2,4,1,6,7" // Original array is not modified
console.log(nums.join(" - ")); // "2 - 4 - 1 - 6 - 7" // Original array is not modified
console.log(nums.fill(0)); // [0, 0, 0, 0, 0] // Original array is modified


const arr1 = [1, 2, 3, [4, 5, 6], 7];
console.log(arr1.flat()); // [1, 2, 3, 4, 5, 6, 7] // Original array is not modified

```

→ [[JavaScript]]