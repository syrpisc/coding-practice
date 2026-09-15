# 2236. 判断根结点是否等于子结点之和

- 题目链接：https://leetcode.cn/problems/root-equals-sum-of-children/

- 难度：简单

- 相关标签：二叉树

- 思路：思路较为简单，直接计算出两个子结点的和，判断是否与根结点相等即可

### 代码

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def checkTree(self, root):
        """
        :type root: Optional[TreeNode]
        :rtype: bool
        """
        l = root.left
        r = root.right
        if root.val == l.val + r.val:
            return True
        else:
            return False
```

- 时间复杂度：O(1)

- 空间复杂度：O(1)

### 笔记
本题的思路并不复杂，难点在于二叉树两个子结点的表示。

在注释部分，题目告诉了我们一个树的结点对象所拥有的成员变量，`val`代表结点的值，`left`代表左子结点，`right`代表右子结点，初始值为`None`。

而在需要补充的函数`checkTree`中，`root`参数正是一个结点对象。

用`root`代表根结点，于是可以令`l`为其左子结点，令`r`为其右子结点，要计算两者之和，即需要将它们的值`val`相加。

#### 又：在python中，`True`和`False`的首字母严格大写，否则报错

#### 因为昨天学习了一下python类与对象的知识，于是今天顺利地看懂了注释部分代码，鼓掌！！

---

### ⭐代码优化

#### 一：代码简化

```python
class Solution(object):
    def checkTree(self, root):
        """
        :type root: Optional[TreeNode]
        :rtype: bool
        """
        return root.val == root.left.val + root.right.val
```

直接使用布尔表达式

#### 二：一般化

本题保证根节点有两个子节点，所以`root.left`和`root.right`一定存在。如果是普通二叉树，需要先判断：

```python
if not root.left or not root.right:
    return False
```