# 方法
方法一：使用循环对输入整数按10取余，取余后取整除以10，然后余数循环乘10，直到取整除以为0停止循环，得到最后反转的数。
注意：在python3中，-123%10是不等于3的，这点是个坑，所以python3实现中加入了负号的判断。

方法二：更加粗暴，直接判断整数是否为负数，标识符用字符来表示，是负数则'-'，不是则空字符，直接将整数转成字符串反转加上前面的标识符符号，后面判断越界即可。（这种方法更快。）