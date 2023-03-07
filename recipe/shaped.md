---
description: 定义一个有序工作台配方
---

# 有序配方

## 配方的形状

不同与其他配方，有序配方需要指定配方的形状。你需要在shape配置项中指定配方的形状，并在source配置项中指定每个字母代表的物品

示例：

```yaml
shape:
  - 'aaa'
  - 'bbb'
  - 'ccc'
source:
  a: 'bedrock'
  b: 'command_block'
  c: 'items:example_item:example_item'
```

{% hint style="info" %}
注意：有序配方的形状必须小于3x3！
{% endhint %}

## 多种合成方式的配置格式

当需要多种合成方式时，首先应该配置multiple为true。此时，shape配置项中应编写形状的列表，每个列表对应一个合成方式。

示例：

```yaml
multiple: true
shape:
  - - 'aaa'
    - 'bbb'
    - 'ccc'
  - - 'dd'
    - 'ee'
source:
  a: 'bedrock'
  b: 'command_block'
  c: 'items:example_item:example_item'
  d: 'diamond'
  e: 'iron_ingot'
```

## 完整的配方文件示例

### 单个合成方式的配方

```yaml
type: shaped
result: bedrock
shape:
  - 'aaa'
  - 'bbb'
  - 'ccc'
source:
  a: 'bedrock'
  b: 'command_block'
  c: 'items:example_item:example_item'
```

### 多个合成方式的配方

```yaml
type: 'shaped'
result: 'items:example_item:example_item'
multiple: true
shape:
  - - 'aaa'
    - 'bbb'
    - 'ccc'
  - - 'dd'
    - 'ee'
source:
  a: 'bedrock'
  b: 'command_block'
  c: 'items:example_item:example_item'
  d: 'diamond'
  e: 'iron_ingot'
```
