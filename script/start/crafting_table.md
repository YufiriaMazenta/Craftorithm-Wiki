---
description: 在配方文件中使用动作系统
---

# 在配方中使用

{% hint style="info" %}
注意：目前只支持工作台配方和锻造台配方使用动作系统。
{% endhint %}

## 控制能否合成

当我们希望玩家要满足某条件时才能合成此配方，我们可以在配方文件中配置condition配置项。格式如下：

```yaml
condition: '<动作语句>'
```

这里的动作语句会在返回结果后使用if进行包装，防止出现意外类型的返回值。

### 示例

#### 玩家有权限"craftorithm.test"权限才能合成

```yaml
condition: 'perm craftorithm.test'
```

#### 玩家有权限"craftorithm.test"权限并且等级高于100级才能合成

```yaml
condition: 'all perm craftorithm.test && level > 100'
```

#### 玩家有权限"craftorithm.test"权限或玩家等级高于100级才能合成

```yaml
condition: 'any perm craftorithm.test || level > 100'
```

#### 玩家名字是"YufiriaMazenta"才能合成

```yaml
condition: 'papi %player_name% == YufiriaMazenta'
```

### 完整的配置文件示例

```yaml
type: 'shaped'
result: 'items:example_item:example_item'
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
  c: 'items:example_item:example_item'
  d: 'diamond'
  e: 'iron_ingot'
unlock: true

condition: 'if all perm craftorithm.perm.example && level >= 100 && papi %player_name% == YufiriaMazenta'
```

## 合成后执行动作

当我们希望玩家合成某配方后执行一些动作，我们可以在配置文件中配置actions配置项。格式如下：

```yaml
actions:
  - '动作1'
  - '动作2'
  ...
```

### 示例

#### 当玩家合成后执行命令/me hello，并且给予玩家1级经验

```yaml
actions:
  - 'command me hello'
  - 'take-level -1'
```

### 完整的配置文件示例

```
type: 'shaped'
result: 'items:example_item:example_item'
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
  c: 'items:example_item:example_item'
  d: 'diamond'
  e: 'iron_ingot'
unlock: true

condition: 'if all perm craftorithm.perm.example && level >= 100 && papi %player_name% == YufiriaMazenta'
actions:
  - 'command me hello'
  - 'take-level -1'
```
