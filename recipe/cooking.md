---
description: 定义一个烧炼配方
---

# 烧炼配方

## 烧炼配方的类型

烧炼配方一共有四种类型，分别为熔炉（furnace）、高炉（blast）、烟熏炉（smoker）和营火（campfire）

## 合成物品的配置格式

对于烧炼配方来说，需要指定烧炼的类型和烧炼的物品，source配置项的配置格式如下

```yaml
source:
  block: <block>
  item: <item>
```

示例：

```yaml
source:
  block: furnace
  item: bedrock
```

## 规定配方的烧炼时间以及烧炼完成的经验值

烧炼时间的配置由time配置项规定，单位为tick，每20tick为1秒，只支持Int（整数）数据，默认值为200

烧炼完成给予的经验值由exp配置项规定，支持Float数据

示例：

```yaml
source:
  block: furnace
  item: command_block
exp: 10
time: 200
```

## 多种合成方式的配置格式

当需要多种合成方式时，首先应该配置multiple为true。此时，source配置项中应配置合成方式的列表。

示例：

```yaml
multiple: true
source:
  - block: furnace
    item: command_block
  - block: smoker
    item: command_block
  - block: campfire
    item: command_block
  - block: blast
    item: command_block
exp: 10
time: 200
```

另外，对于每种合成方式，可以单独指定其烧炼时间和烧炼完成的经验值，未配置的则按照全局值进行设定。

示例：

```yaml
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
  - block: blast
    item: command_block
exp: 10
time: 200
```

上面这段配置中，熔炉配方的烧炼时间为100tick（5秒），烧炼完成的经验值为20；而其他三个配方的烧炼时间都为200tick（10秒），烧炼完成的经验值为10。

## 完整的配置文件示例

### 单个合成方式的配方

```yaml
type: cookingy
result: bedrock
source:
  block: furnace
  item: command_block
exp: 10
time: 200
```

### 多个合成方式的配方

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
  - block: blast
    item: command_block
exp: 10
time: 200
```
