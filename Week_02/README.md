# 学习笔记

## 1、哈希表（Hash table）

查询：O(1)

增加：O(1)

查询：O(1)



## 2、树（Tree）

### 二叉树 Binary Tree

```Python
# Python版 示例代码
class TreeNode:
    def __init__(self, val):
        self.val = val
        self.left, self.right = None, None
```



```Python
# 二叉树遍历 示例代码
"""
前序(Pre-order):根-左-右 
中序(In-order):左-根-右 
后序(Post-order):左-右-根
"""
def preorder(self, root):
    if root: 
        self.traverse_path.append(root.val) 
        self.preorder(root.left) 
        self.preorder(root.right)
    
def inorder(self, root):
    if root:
        self.inorder(root.left) 
        self.traverse_path.append(root.val) 
        self.inorder(root.right)
    
def postorder(self, root):
    if root:
        self.postorder(root.left) 
        self.postorder(root.right) 
        self.traverse_path.append(root.val)
```

### 二叉搜索树 Binary Search Tree

二叉搜索树，也称二叉搜索树、有序二叉树(Ordered Binary Tree)、 排序二叉树(Sorted Binary Tree)，是指一棵空树或者具有下列性质的 二叉树:

- 左子树上所有结点的值均小于它的根结点的值; 

- 右子树上所有结点的值均大于它的根结点的值;
-  以此类推:左、右子树也分别为二叉查找树。 (这就是 重复性!) 

结论:中序遍历是升序排列 

常见操作的时间复杂度:

1. 查询 O(log n)

2. 插入新结点(创建) O(log n)

3. 删除 O(log n)

   

## 3、堆（Heap）

Heap:可以迅速找到一堆数中的最大或者最小值的数据结构。

将根节点最大的堆叫做大顶堆或大根堆，根节点最小的堆叫做小顶堆或小根堆。
常见的堆有二叉堆、斐波那契堆等。

假设是大顶堆，则常见操作(API) :

find-max:O(1)
delete-max:O(logN)
insert (create): O(logN) or O(1)

### 二叉堆性质

通过完全二叉树来实现(注意:不是二叉搜索树) ;

二叉堆(大顶)它满足下列性质:
[性质一]是一棵完全树。
[性质二]树中任意节点的值总是>=其子节点的值;

### 二叉堆实现细节

1.二叉堆一般都通过“数组”来实现

2.假设"第一个元素"在数组中的索引为0的话,则父节点和子节点的位置关系如下:

(01)索引为i的左孩子的索引是(2*i+1);*

(02)索引为i的右孩子的索引是(2i+2);

(03)索引为i的父结点的索引是flor((i-1)/2);

### Insert插入操作

1.新元素一律先插入到堆的尾部

2.依次向上调整整个堆的结构(一直到根即可)   HeapifyUp

### Delete Max删除堆顶操作

1.将堆尾元素替换到顶部(即对顶被替代删除掉)

2.依次从根部向下调整整个堆的结构(一直到堆尾即可)   HeapifyDown