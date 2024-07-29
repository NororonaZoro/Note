# Leetcode 0066.加一

- 标签：数组、数学
- 难度：简单

- [0066. 加一 - 力扣](https://leetcode.cn/problems/plus-one/)

**描述**：给定一个非负整数数组，数组每一位对应整数的一位数字。

**要求**：计算整数加 11 后的结果。

**说明**：

- 1≤ *digits.length* ≤100。
- 0≤ *digits[i]* ≤9。

**示例**：

- 示例 1：

```python
输入：digits = [1,2,3]
输出：[1,2,4]
解释：输入数组表示数字 123，加 1 之后为 124。
```

- 示例 2：

```python
输入：digits = [4,3,2,1]
输出：[4,3,2,2]
解释：输入数组表示数字 4321。
```

**解题思路一**：

刚开始笔者就是正常思路，使用 *for* 循环去一位一位判断，如果有进位则进位，否则直接加跳出循环

但是忽略了一个用例，就是如果是 *9* 这样的数组，加完不仅会进位，还会使一位变成两位

所以感觉从后向前处理数组不太方便

**解题思路二**：

于是笔者首先想到要把数组倒置处理

之后再按照思路一去逐位判断

循环结束后，判断队尾是否为零，若为零则加一位置为一

最后将数组再倒置回来

**代码**：

```python
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:
        digits.reverse()
        for i in range(len(digits)):
            if digits[i] + 1 == 10:
                digits[i] = 0
                continue
            else:
                digits[i] += 1
                break 
        if digits[len(digits) -1] == 0: digits.append(1)
        digits.reverse()
        return digits
```

