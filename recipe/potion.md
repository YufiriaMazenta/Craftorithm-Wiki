---
description: 定义一个酿造配方
---

# 酿造配方

## 合成物品的配置格式

示例：

```yaml
type: potion
result: bedrock
source:
  input: 'command_block'
  ingredient: 'command_block'
```

其中，input代表酿造台下面三个格子的物品，而ingredient则代表放在上面的原料物品

## 多种合成方式的配置格式

示例：

```yaml
multiple: true
source:
  - input: 'command_block'
    ingredient: 'command_block'
  - input: 'bedrock'
    ingredient: 'bedrock'
```

## 完整的配置文件示例

### 单个合成方式的格式

```yaml
type: potion
result: bedrock
source:
  input: 'command_block'
  ingredient: 'command_block'
```

### 多个合成方式的格式

```yaml
type: potion
result: bedrock
multiple: true
source:
  - input: 'command_block'
    ingredient: 'command_block'
  - input: 'bedrock'
    ingredient: 'bedrock'
```
