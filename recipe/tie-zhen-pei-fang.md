---
description: 定义一个铁砧配方
---

# 铁砧配方

{% hint style="info" %}
铁砧配方目前正处于早期阶段，可能会有BUG，若发现BUG请及时反馈！
{% endhint %}

## 合成物品的配置格式

和锻造台配方的格式基本一致。

示例：

```yaml
type: anvil
result: bedrock
source:
  base: 'command_block'
  addition: 'command_block'
```

## 消耗的等级

铁砧配方消耗等级由cost\_level配置项定义。

示例：

<pre class="language-yaml"><code class="lang-yaml"><strong>cost_level: 10
</strong>source:
  base: 'command_block'
  addition: 'command_block'
</code></pre>

## 多种合成方式的配置格式

与锻造台配方的格式基本一致

示例：

```yaml
multiple: true
source:
  - base: 'command_block'
    addition: 'command_block'
  - base: 'bedrock'
    addition: 'bedrock'
```

另外，对于每种合成方式，可以单独指定其消耗的经验值，未配置的则按照全局值进行设定。

示例：

```yaml
cost_level: 10
multiple: true
source:
  - base: 'command_block'
    addition: 'command_block'
  - base: 'bedrock'
    addition: 'bedrock'
    cost_level: 20
```

上面这段配置中，第一个配方消耗的等级为全局值10级，而第二个配方消耗的等级为20级。

## 完整的配置文件示例

### 单个合成方式的格式

```yaml
type: anvil
result: bedrock
cost_level: 10
source:
  base: 'command_block'
  addition: 'command_block'
```

### 多个合成方式的格式

```yaml
type: anvil
result: bedrock
cost_level: 10
multiple: true
source:
  - base: 'command_block'
    addition: 'command_block'
  - base: 'bedrock'
    addition: 'bedrock'
    cost_level: 20
```
