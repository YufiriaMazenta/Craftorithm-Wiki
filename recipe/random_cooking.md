---
description: 定义一个随机烧炼配方
---

# 随机烧炼配方

## 简介

随机烧炼配方是插件定义的特色合成配方，支持1.17+的Spigot服务端。配置格式如下。

```yaml
type: random_cooking
result:
  - '<item> <权重>'
  - '<item> <权重>'
  - '<item> <权重>'
  ...
source:
  block: <block>
  item: <item>
```

和普通烧炼配方唯一的不同在于result配置项的不同。需要指定物品和权重，权重会影响物品的出率，权重越高，概率越高；物品的抽出概率等于其权重占权重总和的比例。

{% hint style="info" %}
注意：物品概率的配置推荐按照概率从高到低配置，原因是插件会默认注册第一个物品的配方到服务器中，由于熔炉本身的限制，如果玩家留第一个物品在熔炉里，其他结果将无法正常烧出，将永远产出相同的物品。
{% endhint %}

{% hint style="info" %}
注意：随机烧炼配方不支持营火类型的烧炼配方！
{% endhint %}

## 完整的配置文件示例

### 单个合成方式的配方

```yaml
type: random_cooking
result:
  - 'iron_ingot 80'
  - 'diamond 5'
  - 'copper_ingot 15'
source:
  block: furnace
  item: bedrock
exp: 10
time: 100
```

### 多个合成方式的配方

```yaml
type: random_cooking
result:
  - 'iron_ingot 80'
  - 'diamond 5'
  - 'copper_ingot 15'
multiple: true
source:
  - block: furnace
    item: bedrock
  - block: smoker
    item: bedrock
  - block: blast
    item: bedrock
exp: 10
time: 100
```
