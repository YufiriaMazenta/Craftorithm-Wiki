---
description: 定义一个无序工作台配方
---

# 无序配方

## 合成物品的配置格式

对于无序配方来说，不需要指定摆放方式，只配置物品列表即可。

示例：

```yaml
source:
  - 'bedrock'
  - 'bedrock'
  - 'bedrock'
```

{% hint style="info" %}
注意：如果物品列表的长度超过9，只会取前9个物品
{% endhint %}

## 多种合成方式的配置格式

当需要多种合成方式时，首先应该配置multiple为true。此时，source配置项中应配置物品列表的列表，每个列表指定一种合成方式。

示例：

```yaml
multiple: true
source:
  - - 'bedrock'
    - 'bedrock'
    - 'bedrock'
  - - 'command_block'
    - 'command_block'
    - 'command_block'
```

## 完整的配置文件示例

### 单个合成方式的配方

```yaml
type: 'shapeless'
result: 'bedrock'
source:
  - 'bedrock'
  - 'bedrock'
  - 'bedrock'
```

### 多个合成方式的配方

```yaml
type: 'shapeless'
result: 'bedrock'
multiple: true
source:
  - - 'bedrock'
    - 'bedrock'
    - 'bedrock'
  - - 'command_block'
    - 'command_block'
    - 'command_block'
```
