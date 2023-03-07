---
description: 物品系统的配置构成
---

# 配置构成

## 物品的存储方式

在插件中，所有的物品都存储在plugins/Craftorithm/items文件夹中。

### 命名空间

一般情况下，命名空间即为文件名，每个命名空间可以有多个物品，不同的命名空间中可以有相同名字的物品。

### 物品名

一般情况下，物品的配置根节点即为物品名字。

## 物品的配置组成

### material

物品的材质

### amount

物品的数量

### nbt

所有的NBT信息都存储在此配置项下

### 一般样式

#### \<namespace>.yml

```
item_name:
  material: <material>
  amount: <amount>
  nbt:
    <nbt>
```
