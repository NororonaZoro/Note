# Leetcode 0458.最大连续1的个数

- 标签：数组
- 难度：简单

- [0485. 最大连续 1 的个数 - 力扣](https://leetcode.cn/problems/max-consecutive-ones/)

**描述**：给定一个二进制数组 nums*n**u**m**s*， 数组中只包含 00 和 11。

**要求**：计算其中最大连续 11 的个数。

**说明**：

- 1≤ *nums.length* ≤105。
- *nums[i]* 不是 *0* 就是 *1*。

**示例**：

- 示例 1：

```python
输入：nums = [1,1,0,1,1,1]
输出：3
解释：开头的两位和最后的三位都是连续 1 ，所以最大连续 1 的个数是 3.
```

- 示例 2：

```python
输入：nums = [1,0,1,1,0,1]
输出：2
```

**解题思路**：

该题比较简单，从头开始遍历，遇到一计数器就加一，当遇到零时，则当前统计结束

计数器与之前存储最大连续数继续比较，若大于则覆盖，否则不做操作

> 注意：最后若以 *1* 结尾，循环中则不会将最后一次计数器与统计数比较，导致统计数不是最大

**代码**：

```python
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        num, cnt = 0, 0
        for i in range(len(nums)):
            if nums[i] == 1:
                cnt += 1
            else:
                if num < cnt: num = cnt
                cnt = 0
        if num < cnt: num = cnt
        return num        
```

