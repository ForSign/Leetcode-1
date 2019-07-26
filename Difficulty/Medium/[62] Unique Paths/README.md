# 问题描述

一个机器人位于一个 m x n 网格的左上角 （起始点在下图中标记为“Start” ）。

机器人每次只能向下或者向右移动一步。机器人试图达到网格的右下角（在下图中标记为“Finish”）。

问总共有多少条不同的路径？

![img](assets/robot_maze.png)

例如，上图是一个7 x 3 的网格。有多少可能的路径？

说明：m 和 n 的值均不超过 100。

# 例子

```bash
输入: m = 3, n = 2
输出: 3
解释:
从左上角开始，总共有 3 条路径可以到达右下角。
1. 向右 -> 向右 -> 向下
2. 向右 -> 向下 -> 向右
3. 向下 -> 向右 -> 向右

输入: m = 7, n = 3
输出: 28
```

# 方法

典型的棋盘填充数值，且原问题可以通过子问题进行求解。第一行和第一列都是1，因为只有当只有一行或者一列的时候，就只有一种走法。当为多行多列的时候，当前值（m行n列）等于子问题（m-1行n列）和子问题（m行n-1列）的求和，很好理解。

在[讨论](https://leetcode.com/problems/unique-paths/discuss/22954/C%2B%2B-DP)中发现一种十分精巧的动态规划解决方案，内存占用为O(1). 时间不变。观察到了每一行是上一行的叠加。

```c++
class Solution {
public:
    int uniquePaths(int m, int n) {
        vector<int> cur(n, 1);
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                cur[j] += cur[j - 1];
            }
        }
        return cur[n - 1];
    }
};
```