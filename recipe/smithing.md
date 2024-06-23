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

## 1.20的新锻造配方

对于插件来说，1.20新增的锻造台配方新增了两个参数，分别为type和template，意思是类别和模板。type有trim和transform两种类型，分别为装饰类型和转化类型；template用于指定锻造模板。示例格式如下：

```yaml
type: smithing
result: bedrock
multiple: true
source:
  base: 'command_block'
  addition: 'command_block'
  type: 'transform'
  template: 'diamond'
```

对于装饰类型（trim）配方，配方的result将会被忽略，他的结果会为当前的护甲附加上模板提供的装饰纹理。

对于转化类型（transform）配方，配方的结果将会保留参数base所指定物品的NBT。

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

1.20的新锻造配方示例如下：

```yaml
type: smithing
result: bedrock
multiple: true
source:
  - base: 'command_block'
    addition: 'command_block'
    type: transform
    template: diamond
  - base: 'bedrock'
    addition: 'bedrock'
    type: trim
    template: diamond
```

## 是否保留原材料NBT

当此配置为true时，合成结果的NBT/组件将复制原材料的NBT；当为false时，合成结果的NBT/组件将为设置时的物品

#### 配置示例

```yaml
type: smithing
result: bedrock
multiple: true
source:
  base: 'command_block'
  addition: 'command_block'
  type: 'transform'
  template: 'diamond'
  copy_nbt: true
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
