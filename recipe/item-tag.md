# 在配方中使用物品Tag

除铁砧配方以外，其余配方可以在指定合成材料时使用原版的物品Tag。

大致意思就是，比如说我希望一个配方允许所有的木板都可以用作材料，那么可以使用`tag:planks`作为合成材料。

示例：

```yaml
type: shaped
result: bedrock
shape:
  - 'aaa'
  - 'bbb'
  - 'ccc'
source:
  a: 'bedrock'
  b: 'command_block'
  c: 'tag:planks'
```

此时，配方的第三行支持所有类型的木板作为合成材料使用。
