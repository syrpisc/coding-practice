# 1486. 数组异或操作

- 题目链接：https://leetcode.cn/problems/xor-operation-in-an-array/

- 难度：简单

- 相关标签：位运算

- 思路：从start，即nums数组的第一个值开始，依次做按位异或的运算，并将值存储为result。

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
用`^`表示按位异或（XOR）

### ⭐代码优化