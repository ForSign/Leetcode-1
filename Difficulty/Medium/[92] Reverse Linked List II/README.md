# 问题描述

反转从位置 m 到 n 的链表。请使用一趟扫描完成反转。

**说明:**
1 ≤ m ≤ n ≤ 链表长度。

# 例子

```bash
输入: 1->2->3->4->5->NULL, m = 2, n = 4
输出: 1->4->3->2->5->NULL
```

# 方法

根据对称性进行交换val，使用一个vector存储之前的指针，过了对称点，对称交换vector中的值。