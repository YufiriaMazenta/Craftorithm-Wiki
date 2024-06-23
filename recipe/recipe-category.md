---
description: 配方分类会决定配方在玩家配方书中所属的选项卡
---

# 配方分类

{% hint style="info" %}
注意：配方分类仅在1.10.0以上版本插件可用
{% endhint %}

## 工作台配方（有序、无序）

工作台配方中，配方类型可为building（建筑方块）、redstone（红石）、equipment（工具）和misc（物品）

## 烧炼配方（熔炉、高炉、烟熏炉）

配方类型可为food（食物）、blocks（方块）和misc（物品）

## 编写格式

```yaml
category: <配方分类>
```

## 示例配置

工作台配方 | Crafting Recipe：

```yaml
type: 'shaped'
result: 'diamond_sword'
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
  c: 'diamond'
  d: 'barrier'
  e: 'chain_command_block'
unlock: true
sort_id: 1
category: building
```

烧炼配方 | Smelting Recipe：

```yaml
type: cooking
result: bedrock
multiple: true
source:
  - block: furnace
    item: command_block
    exp: 20
    time: 100
  - block: smoker
    item: command_block
  - block: campfire
    item: command_block
  - block: blast_furnace
    item: command_block
exp: 10
time: 200
category: blocks
```
