---
description: 定义一个铁砧配方
---

# 铁砧配方

## 合成物品的配置格式

```yaml
type: anvil
result: bedrock
source:
  base: diamond
  addition: iron_ingot
  copy_nbt: true
  cost_level: 1
```

其中，base代表铁砧的第一个物品，addition代表铁砧的第二个物品，铁砧配方支持识别原料数量；copy\_nbt代表是否保留nbt，此项控制结果是否保留第一个物品的nbt，不设置默认为true，cost\_level代表消耗的经验等级，使用shift+点击批量合成时也会扣除对应数量的经验。

## 多种合成方式的配置格式

```yaml
type: anvil
result: bedrock
source:
  - base: diamond
    addition: iron_ingot
    copy_nbt: true
    cost_level: 1
  - base: iron_ingot
    addition: diamond
    copy_nbt: true
```

