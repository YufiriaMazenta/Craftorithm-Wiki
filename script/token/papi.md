---
description: 对PlaceholderAPI变量进行判断
---

# Papi

## 格式

```
papi <placeholder> [运算符] [数值]
```

由于PlaceholderAPI返回的结果大部分情况下为字符串，此语句支持的运算符略微有些不同。

当PlaceholderAPI的返回值和进行比较的内容都是数字时，将运行与Level语句相似的运算符解析。

而当PlaceholderAPI的返回值或进行比较的内容其中一项不是数字时，会将这两项视为字符串进行比较；而字符串在进行比较时按照以下规则：

```
<、>、<=、>=将对两个字符串的长度进行比较，并返回结果
=/==、!=将对两个字符串本身内容进行比较
```

另外，字符串的比较还支持两个特有的运算符，分别为has和in，规则如下：

```
has将判断左侧字符串是否包含右侧字符串，例如hello has hel将返回true
in将判断右侧字符串是否包含左侧字符串，例如hello in helloworld将返回true
```
