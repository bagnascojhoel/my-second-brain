#leetcode #development_career #javascript

[[15/02/2022]]
# [Single Number](https://leetcode.com/problems/single-number/)
Took me 09:18 to came up with:
```javascript
// Complexity 2*O(N²)
var singleNumber = function(nums) {
    for (let num of nums)
        if (nums.indexOf(num) === nums.lastIndexOf(num))
            return num;
};
```

The best solution I foud was:
```javascript
/** It should be looked at as bits. Otherwise it will not make much sense.
	When XOR a 0100 (4) with 0001 (1) -> 0101
	So, if your XOR a number with 0, it will be itself -> 0100 ^ 0000 = 0100
	And XOR a number with itself, will be 0 -> 0100 ^ 0100 = 0000
	So in this algorithm, when 0 ^ <number A> will be <number A>, if your XOR that result with <number B> and then the number repeats itself, it will go back to being <number A>.
**/
var singleNumber = function(nums) {
    var result;
    for (let num of nums)
        result = result ^ num;
    
    return result;
};
```