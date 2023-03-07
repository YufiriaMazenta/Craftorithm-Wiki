---
description: 在function.yml中定义的动作组
---

# 函数

## 定义

我们可以在plugins/Craftorithm/function.yml中将多个动作打包为一个组，称之为函数。

## 格式

```yaml
函数名:
  - '语句1'
  - '语句2'
  ...
```

在此处定义的函数体，会被视为语句进行解析，可以被当作语句使用。

### 示例

function.yml

```yaml
example:
  - 'if level > 100'
  - |-
    take-level 10
    return
  - 'take-level 1'
test:
  - return all perm craftorithm.perm.example && level >= 100 && papi %player_name% == YufiriaMazenta
```

recipes/example\_shaped.yml

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

condition: 'test'
actions:
  - 'example'
```
