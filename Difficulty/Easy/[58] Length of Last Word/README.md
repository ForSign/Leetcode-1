# 问题描述
给定一个字符串s由大写/小写字母和空空格字符' '组成，返回字符串中最后一个单词的长度。如果最后一个单词不存在，返回0。

注意:单词被定义为由非空格字符组成的字符序列。
# 例子
```bash
Input: "Hello World"
Output: 5
```

# 方法
先找到第一个出现非空字符的索引， 然后递减倒着进行索引，直到遇到空字符结束。