---
description: 定义一个切石机配方
---

# 切石机配方

## 合成物品的配置格式

对于切石机配方来说，需要提供的合成物品只有一个。

格式：

```yaml
source: <item>
```

示例：

```yaml
source: command_block
```

## 多个结果

不同于其他配方，切石机可以有多种合成结果，当result项为字符串列表时，将会创建出多个不同结果的配方。

示例：

```yaml
result:
  - bedrock
  - diamond
  - iron_ingot
source: command_block
```

以上配置将会创建出三个配方，分别为命令方块切为基岩、钻石和铁锭。

## 多种合成方式的配置格式

当需要多种合成方式时，首先应该配置multiple为true。此时，source配置项中应指定物品列表。

示例：

```yaml
multiple: true
source:
  - command_block
  - bedrock
```

## 完整的配置文件示例

### 单个合成方式&单个结果的配方

```yaml
type: stone_cutting
result: bedrock
source: command_block
```

### 单个合成方式&多个结果的配方

```yaml
type: stone_cutting
result:
  - bedrock
  - diamond
  - iron_ingot
source: command_block
```

### 多个合成方式&单个结果的配方

```yaml
type: stone_cutting
result: bedrock
multiple: true
source:
  - command_block
  - bedrock
```

### 多个合成方式&多个结果的配方

```yaml
type: stone_cutting
multiple: true
result:
  - bedrock
  - diamond
  - iron_ingot
source:
  - command_block
  - bedrock
```
