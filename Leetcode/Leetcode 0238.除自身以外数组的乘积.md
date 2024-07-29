# Leetcode 0238.除自身以外数组的乘积

- 标签：数组、前缀和
- 难度：中等

- [0238. 除自身以外数组的乘积 - 力扣](https://leetcode.cn/problems/product-of-array-except-self/)

**描述**：给定一个数组 *nums*。

**要求**：返回数组 *answer*，其中 *answer[i]*  等于 *nums* 中除 *nums[i]* 之外其余各元素的乘积。

**说明**：

- 题目数据保证数组 *nums* 之中任意元素的全部前缀元素和后缀的乘积都在 *32* 位整数范围内。
- 请不要使用除法，且在 *O(n)* 时间复杂度内解决问题。
- **进阶**：在 *O(1)* 的额外空间复杂度内完成这个题目。
- 2≤ *nums.length* ≤105。
- −30≤ *nums[i]* ≤30。

**示例**：

- 示例 1：

```python
输入: nums = [1,2,3,4]
输出: [24,12,8,6]
```

- 示例 2：

```python
输入: nums = [-1,1,0,-3,3]
输出: [0,0,9,0,0]
```

**解题思路**：

笔者刚开始想的是两层循环去算，然后将第二层循环优化成 *O(n)* 但是没能实现

说实话笔者都没想到题中给的限制不让用的除法方法

**解析思路**（太巧妙了）：

本题的难点在于 **不能使用除法** ，即需要 **只用乘法** 生成数组 *ans* 。根据题目对 *ans[i]* 的定义，可列出下图所示的表格。

根据表格的主对角线（全为 *1* ），可将表格分为 **上三角** 和 **下三角** 两部分。分别迭代计算下三角和上三角两部分的乘积，即可 **不使用除法** 就获得结果。

> 下图中 A = *nums*  , B = *ans*

![1624619180-vpyyqh-Picture1](https://gitee.com/lu-hua7/picture/raw/master/1624619180-vpyyqh-Picture1.png)

**算法流程**：

1. 初始化：数组 *ans* ，其中 *ans[0]=1* ；辅助变量 *tmp=1* 。
2. 计算 *ans[i]* 的 **下三角** 各元素的乘积，直接乘入 *ans[i]* 。
3. 计算 *ans[i]* 的 **上三角** 各元素的乘积，记为 *tmp* ，并乘入 *ans[i]* 。
4. 返回 *ans* 。

**代码**：

```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        ans, tmp = [1] * len(nums), 1
        for i in range(1, len(nums)):
            ans[i] = ans[i - 1] * nums[i - 1]
        for i in range(len(nums) - 2, -1, -1):
            tmp *= nums[i + 1]
            ans[i] *= tmp
        return ans

```

