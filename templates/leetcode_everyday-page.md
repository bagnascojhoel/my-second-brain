#leetcode #development_career 

Today, <% tp.file.creation_date("DD-MM-YYYY") %>, I will solve
- [Swap Nodes in Pairs](https://leetcode.com/problems/swap-nodes-in-pairs/), took me XXXX, and the solution I came up with was:
```
class Solution {
    public ListNode swapPairs(ListNode initialHead) {
        ListNode finalHead = null;
        ListNode previousNode = null;
        ListNode firstNode = initialHead;
        while (firstNode != null) { 
            var lastNode = firstNode.next;
            
            if (finalHead == null)
                finalHead = lastNode != null ? lastNode : firstNode;        
            
            if (lastNode != null) {
                var nextNode = lastNode.next;

                if (previousNode != null)
                    previousNode.next = lastNode;
                
                firstNode.next = nextNode;
                lastNode.next = firstNode;
                
                previousNode = firstNode;
                firstNode = nextNode;
            } else {
                firstNode = lastNode;
            }
    
        }
        
        return finalHead;
    }
}
```

Could use some improvement, based on [this solution](https://leetcode.com/problems/swap-nodes-in-pairs/discuss/1774708/C%2B%2BorVisual-Image-how-links-change-or-Explained-every-step-or-Commented-code).
<% tp.file.creation_date %>