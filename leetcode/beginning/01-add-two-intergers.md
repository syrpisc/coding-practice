# 2235. 两整数相加

- 题目链接：https://leetcode.cn/problems/add-two-integers/

- 难度：简单

- 思路：直接返回两数之和

- 时间复杂度：O(1)

- 空间复杂度：O(1)

### 代码
```python
class Solution(object):
    def sum(self, num1, num2):
        """
        :type num1: int
        :type num2: int
        :rtype: int
        """
        return num1+num2
```

### 笔记
这道题是入门题中的第一题，对于刚开始刷题的我非常友好。然而在这道简单的题目中，我注意到这个函数的定义中有一个`self`参数，这在我平常编写代码时一般不会使用。以下是对该参数作用的一点探究：

`self`表示当前类的实例对象本身，习惯上命名为`self`，用于接收调用这个方法的实例对象。

如果要调用上面这段代码，可以这样写：
```python
s = Solution()
s.sum(1, 2)
```

而这就相当于
```python
Solution.sum(s, 1, 2)
```

也就是说，`s`被传给了`self`。

在这个例子中，虽然方法里没用到`self`，但因为它被定义成**实例方法**，所以必须保留这个参数。

如果不需要实例，可以写成静态方法：
```
class Solution(object):
    @staticmethod
    def sum(num1, num2):
        return num1 + num2
```