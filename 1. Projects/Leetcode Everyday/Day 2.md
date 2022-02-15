#leetcode #development_career #elixir

Today, [[2022-02-15]], I will solve
- [Single Number](https://leetcode.com/problems/single-number/), took me XXXX, and the solution I came up with was:
```javascript
// Complexity 2*O(N)
var singleNumber = function(nums) {
    for (let num of nums)
        if (nums.indexOf(num) === nums.lastIndexOf(num))
            return num;
};
```