#leetcode #development_career #go

[[18/02/2022]]
# [Remove K Digits](https://leetcode.com/problems/remove-k-digits/)
Took me 01:08:12 to come up with (but it doesn't work for every scenario):
```go
func removeKdigits(num string, k int) string {
    smallest unit, err := strconv.Atoi(num)
    if err == nil {
        smallest = findSmallest(num, k, 0, smallest)
        return strconv.Itoa(smallest)
    } else {
        fmt.Println("Something is wrong." + num)
        return num
    }
}

func findSmallest(num string, maximumToRemove int, currentlyRemoved int, smallest int) int {
    if isBlank(num) {
        return 0;
    }
    
    currentNumber, err := strconv.Atoi(num)
    
    if err != nil {
        fmt.Println("Something is wrong." + num)
    }
    
    var newSmallest int = smallest
    if currentNumber < smallest {
        newSmallest = currentNumber
    }
    
    if (currentlyRemoved == maximumToRemove) {
        return newSmallest
    }
    
    for i:=0; i < len(num); i++ {
        valueFound := findSmallest(removeAt(num, i), maximumToRemove, currentlyRemoved + 1, newSmallest)
        if (valueFound < newSmallest) {
            newSmallest = valueFound
        }
    }
    
    return newSmallest
}

func isBlank(aString string) bool {
    return strings.TrimSpace(aString) == ""
}

func removeAt(aString string, index int) string {
    unicodeArr := []rune(aString)
    unicodeArr = append(unicodeArr[0:index], unicodeArr[index+1:]...)
    return string(unicodeArr)
}
```
### Problematic Scenarios
- There are `num` inputs that are too big for a `int` conversiont