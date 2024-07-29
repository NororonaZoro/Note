# Leetcode 0724.寻找数组的中心下标

- 标签：数组、前缀和
- 难度：简单

- [0724. 寻找数组的中心下标 - 力扣](https://leetcode.cn/problems/find-pivot-index/)

**描述**：给定一个数组 *nums* 。

**要求**：找到「左侧元素和」与「右侧元素和相等」的位置，若找不到，则返回 −1−1。

**说明**：

- 1≤ *nums.length* ≤104。
- −1000≤ *nums[i]* ≤1000。

**示例**：

- 示例 1：

```python
输入：nums = [1, 7, 3, 6, 5, 6]
输出：3
解释：
中心下标是 3 。
左侧数之和 sum = nums[0] + nums[1] + nums[2] = 1 + 7 + 3 = 11，
右侧数之和 sum = nums[4] + nums[5] = 5 + 6 = 11，二者相等。
```

- 示例 2：

```python
输入：nums = [1, 2, 3]
输出：-1
解释：
数组中不存在满足此条件的中心下标。
```

**解题思路**：

首先笔者想的是双指针，但是仔细想了想如果两个指针都动的话，就很难找到正确答案，所以就卡住了

**解析思路**：

题目仅说明是整数数组，无其他已知条件，因此考虑直接遍历数组。

设索引 i 对应变量「左侧元素相加和 *sum_left* 」和「右侧元素相加和 *sum_right* 」。
遍历数组 *nums* ，每轮更新 *sum_left* 和 *sum_right* 。
遍历中，遇到满足 *sum_left == sum_right* 时，说明当前索引为中心下标，返回即可。
若遍历完成，仍未找到「中心下标」，则返回 -1 。
初始化时，相当于索引 *i=−1* ，此时 *sum_left = 0* , *sum_right = 所有元素的和* 。

**笔者理解**：

笔者理解的是左边从无也就是零开始，右边包含整个，然后遍历数组从第一个位置作为中间

每次去比较两边之和是否相等，若找到则返回位置，若遍历完未找到则返回-1

**代码**：

```python
class Solution:
    def pivotIndex(self, nums: List[int]) -> int:
        sum_left, sum_right = 0, sum(nums)
        for i in range(len(nums)):
            sum_right -= nums[i]
            if sum_left == sum_right:
                return i
            sum_left += nums[i]
        return -1
```

