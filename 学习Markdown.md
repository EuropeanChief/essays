# 这是标题
未加粗 **加粗**
***斜体加粗***
*斜体字*
~~加了删除线的文字~~
==高亮==
# 引用

>这是引用的内容1
>>这是引用2
>>>这是引用3

# 分割线

---
----
***
****

# 图片

！[显示在图片下的文字](http://localhost:8080/F:/其他/photo/灯明三千竖图.jpg)

# 超链接
语法：[超链接名](超链接地址 "超链接title") title可加可不加
示列：[简书](http://jianshu.com)

# 列表
1.无序列表
- 列表内容（-）
+ 列表内容（+）
* 列表内容（*）
2.有序列表
数字加点

#列表嵌套
语法：上下级之间敲三个空格
- 无序列表1
   
   1.有序列表
   2.有序

+ 一级无序
   
   1.二级有序
   2.二级有序

1.一级有序
   
   - 二级无序
   - 二级无序

2.一级有序
   
   + 二级无序
   + 二级无序

# 表格
1.语法
   表头|表头|表头
   ---|:---:|---:
   内容|内容|内容
   内容|内容|内容

   第二行分割表头和内容
   - 有一个就可以
   - 文字默认居左，两边加：表示文字居中
   - 右边加：表示文字居右
   - 原生语法最两边都需要加| ，此处省略

2.实例

姓名|身高|来源
--|:--:|--:
血小板|满矮|工作细胞
小圆|不高|魔法少女小圆
贾琏|不知道|红楼梦

# 代码
1.单行代码
`代码内容需要使用“``”包起来`
2.代码块
```
需要使用```包起来，且```单独占一行
```

# 流程图
```flow
st=>start:开始
op=>operation:我的 operation
cond=>condition：Yes or No?
e=>end
st->op-cond
cond(Yes)->e
cond(No)->op
&```

