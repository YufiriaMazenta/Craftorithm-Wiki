---
description: 判断是否满足要求
---

# If

## 格式

```
if <语句>
```

if在解析时，将会先运行后面的语句，并将返回的值转化为boolean类型，也可以if套if。当然，直接写true或者false也是可以正常解析的。

{% hint style="info" %}
注意：当某语句的返回值不是布尔类型，也不是字符串类型时，将会依据对象是否为null返回结果。
{% endhint %}

与其他返回Boolean类型的语句不同，if能够控制下一个语句是否执行，起到控制执行流程的作用。

示例：

```
- 'if false'
- 'command me hello'
- 'command me hello2'
```

上述语句块中，玩家将只会执行/me hello2命令，而不会执行/me hello命令。

此外，插件也提供了类似代码块的编写方式来使得if语句可以控制多条动作的执行。

示例：

```
- if false
- |-
    command me hello
    command me nice to meet you
- command me hello2
```

此时，玩家将跳过执行命令/me hello和/me nice to meet you，直接执行/me hello2。
