# 在配方中使用其他插件的物品

目前插件支持从ItemsAdder、Oraxen和MythicMobs获取物品，格式如下：

使用ItemsAdder的物品：

```yaml
'items_adder:<item_name>'
```

使用Oraxen的物品

```
'oraxen:<item_name>'
```

使用MythicMobs的物品

```
'mythic_mobs:<item_name>'
```

示例：

```yaml
type: shaped
result: items_adder:icon_arrow_chest
shape:
  - 'aaa'
  - 'bbb'
  - 'ccc'
source:
  a: 'bedrock'
  b: 'command_block'
  c: 'oraxen:bedrock_pickaxe'
```
