---
description: 定义一个随机烧炼配方
---

# 随机烧炼配方

## 简介

随机烧炼配方是插件定义的特色合成配方，配置格式如下。

```yaml
type: random_cooking
result:
  - '<item> <概率>'
  - '<item> <概率>'
  - '<item> <概率>'
  ...
source:
  block: <block>
  item: <item>
```

和普通烧炼配方唯一的不同在于result配置项的不同。需要指定物品和概率，概率的总和不能超过1.0，超过1.0的部分将不会生效，若总和小于1.0，剩余的部分将补全空气物品。普通熔炉的配置项都可以在此处生效。

{% hint style="info" %}
注意：物品概率的配置推荐按照概率从高到低配置，原因是插件会默认注册第一个物品的配方到服务器中，如果玩家留第一个物品在熔炉里，将永远产出相同的物品。
{% endhint %}

{% hint style="info" %}
注意：随机烧炼配方不支持营火类型的烧炼配方！
{% endhint %}

## 完整的配置文件示例

### 单个合成方式的配方

```yaml
type: random_cooking
result:
  - 'iron_ingot 0.8'
  - 'diamond 0.05'
  - 'copper_ingot 0.15'
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
  - 'iron_ingot 0.8'
  - 'diamond 0.05'
  - 'copper_ingot 0.15'
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
