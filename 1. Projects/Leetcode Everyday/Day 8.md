#leetcode #development_career #go #data_structures

[[21/02/2022]]
# [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
Took me 22:22 to come up with:
```go
func containsDuplicate(nums []int) bool {
    var removed []int;
    for i, num := range nums {
        if contains(num, removed) {
            return true;
        } else {
            removed = append(removed, nums[i])
        }
    }
    
    return false;
}

func contains(expected int, nums []int) bool {
    for _, num := range nums {
        if (num == expected) {
            return true;
        }
    }
    
    return false;
}
```

It seems that searching for a duplicate after a sort is the quickest way. Even thoug there is a sort, propably most languages already have implemented good algorithms to handle that.
