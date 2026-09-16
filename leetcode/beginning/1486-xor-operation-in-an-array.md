# 1486. 数组异或操作

- 题目链接：https://leetcode.cn/problems/xor-operation-in-an-array/

- 难度：简单

- 相关标签：位运算

- 思路：（较复杂的话可另起标题）

### 代码

```python
class Solution(object):
    def xorOperation(self, n, start):
        """
        :type n: int
        :type start: int
        :rtype: int
        """
        i = 1
        result = start
        while i < n:
            result ^= (start + 2*i)
            i += 1
        return result
```

- 时间复杂度：O(n)

- 空间复杂度：O(1)

### 笔记

### ⭐代码优化