---
description: 判断多条语句是否符合要求
---

# All

## 格式

```
all <语句1> && [语句2] && [语句3] ...
```

all语句在后续的所有语句返回值都为true时才会返回true，例如

```
all true && false
```

将会返回false

另外，all本身也可以当作if使用，无需使用if再次包装返回值。
