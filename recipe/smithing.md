---
description: 定义一个锻造台配方
---

# 锻造配方

## 合成物品的配置方式

对于锻造台配方来说，需要提供两个物品，分别为基础物品和附加材料，在插件中，分别以base和addition指代他们。通俗的说，锻造台左边的物品为base，右边的物品为addition。

格式：

```yaml
source:
  base: <item>
  addition: <item>
```

示例：

```yaml
source:
  base: command_block
  addition: bedrock
```

## 多种合成方式的配置格式

当需要多种合成方式时，首先应该配置multiple为true。此时，source配置项中应配置物品列表的列表，每个列表指定一种合成方式。

示例：

```yaml
multiple: true
source:
  - base: 'command_block'
    addition: 'bedrock'
  - base: 'bedrock'
    addition: 'command_block'
```

## 完整的配置文件示例

### 单个合成方式的配方

```yaml
type: smithing
result: bedrock
source:
  base: 'command_block'
  addition: 'command_block'
```

### 多个合成方式的配方

```yaml
type: smithing
result: bedrock
multiple: true
source:
  - base: 'command_block'
    addition: 'command_block'
  - base: 'bedrock'
    addition: 'bedrock'
```
