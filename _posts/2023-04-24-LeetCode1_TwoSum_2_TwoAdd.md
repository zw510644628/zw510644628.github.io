**对于LeetCode第一道题目两数之和这道题，我们有如下思考：**\
对于一个元素nums[i]，我们需要知道是否存在另一个元素nums[j]的值为target - nums[i]，我们用一个哈希表记录每个元素的值到索引的映射，这样就能快速判断数组中是否有一个值为target - nums[i]的元素了。

附上python代码如下：
```python3
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        valToIndex = {};
        for i in range(len(nums)):
            res = target - nums[i];
            if res in valToIndex:
                return [valToIndex[res], i];
            valToIndex[nums[i]] = i;
        return [];
```
运行效果如图：\
![image](https://user-images.githubusercontent.com/50043212/233990867-84fd9622-9ff0-49d9-b698-07d8ca2cf7af.png)\
之后便可考虑进一步优化代码的时间及内存开销了。

**对于LeetCode第二道题目两数相加这道题，我们有如下思考：**\
我们用到了dummy节点。此外，考虑进位和链表为空的情况，最后返回要去除dummy节点的头结点。

附上python代码如下：
```python3
# @lc code=start
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        p1 = l1;
        p2 = l2;
        dummy = ListNode(-1);
        p = dummy;
        #int val;
        remainder = 0;
        while p1 or p2 or remainder:
            val = remainder;
            if p1:
                val += p1.val;
                p1 = p1.next;
            if p2:
                val += p2.val;
                p2 = p2.next;
            remainder, val = divmod(val, 10);
            
            p.next = ListNode(val);
            p = p.next;
        return dummy.next;
```
运行效果如图：\
![image](https://user-images.githubusercontent.com/50043212/234016995-00e30203-1f46-4f46-b4e2-929ce924382c.png)

