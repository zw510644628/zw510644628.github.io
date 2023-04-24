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
