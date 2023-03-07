---
description: Craftorithm生成的默认配置文件
---

# 默认配置

## 配置文件

{% tabs %}
{% tab title="config.yml" %}
```yaml
#插件版本，涉及到自动更新config.yml内容，一般情况下请勿改动
version: 1.0.0
#是否开启版本更新检查
check_update: true
#是否移除所有的原版配方
remove_all_vanilla_recipe: false
#含有此Lore的物品不能参与合成，可以使用正则表达式
lore_cannot_craft: '.*不可用于合成.*'
#是否将全部由插件定义的原版配方都为玩家在配方书中解锁，默认为true
#也可以在每个配方的配置文件里定义是否解锁，配方配置文件中的优先级高于此处的优先级
all_recipe_unlocked: false
#是否启用插件铁砧配方
enable_anvil_recipe: true
```
{% endtab %}

{% tab title="lang.yml" %}
```yaml
prefix: '&8[&3Craftorithm&8]'
unsupported_version: '<prefix> 不支持的版本'
new_version: '<prefix> &a检测到有新版本<new_version>, 请及时更新到新版本'

#使用命令的一些反馈消息
command:
  no_perm: '<prefix> &c你没有使用此命令的权限'
  player_only: '<prefix> &c只有玩家才能执行此命令'
  not_enough_param: '<prefix> &c命令缺少参数，缺少<number>个参数'
  undefined_subcmd: '<prefix> &c未定义的子命令'
  item:
    save:
      success: '<prefix> &a物品保存成功'
      failed_save_air: '<prefix> &c物品保存失败，原因：不能保存不存在的物品'
    give:
      success: '<prefix> &a物品获取成功'
      not_exist_item: '<prefix> &c不存在物品 <item_name>'
      player_offline: '<prefix> &c该玩家不在线或不存在'
  reload:
    success: '<prefix> &a插件重载成功'
    exception: '<prefix> &c插件重载过程中发生错误，请查看控制台'
  remove:
    success: '<prefix> &a配方删除成功'
    not_exist: '<prefix> &c配方不存在'
  version: '<prefix> &a插件版本：<version>'
  create:
    not_exist_type: '<prefix> &c不存在的配方类型'
  run_arcenciel:
    success: '<prefix> &a运行成功，耗时<time>ms'

#Arcenciel脚本的提示消息
arcenciel:
  not_enough_param: '<prefix> &c语句"<statement>"不完整'
  unknown_token: '<prefix> &c未定义的关键词或函数<token>'

#插件加载的反馈信息
load:
  finish: '<prefix> &a插件加载完毕'
  recipe_load_exception: '<prefix> &c加载配方<recipe_name>时出现错误'
  item_load_exception: '<prefix> &c加载物品<item_name>时出现错误'
  vault_success: '<prefix> &a发现经济插件,已挂钩'
  vault_failed: '<prefix> &c未发现经济插件,金钱检查将不会生效'
  points_success: '<prefix> &a发现点券插件,已挂钩'
  points_failed: '<prefix> &c未发现点券插件,点券检查将不会生效'
```
{% endtab %}

{% tab title="function.yml" %}
```yaml
example:
  - if any test2 || all test && test2 || true
  - |-
    command me hello
    command me nice to meet you
    return true
  - command me hello2
  - return run test2
  - command me hello3
test:
  - return false
test2:
  - return true
```
{% endtab %}

{% tab title="removed_recipes" %}
```yaml
```
{% endtab %}
{% endtabs %}

## 合成配方

{% tabs %}
{% tab title="有序配方" %}
#### example\_shaped.yml

```yaml
#配方的类型
type: 'shaped'
#配方的结果，使用items:<file_name>:<item_name>格式可以调用插件保存的物品
result: 'items:example_item:example_item'
#是否多种合成方式
multiple: true
#配方的形状
shape:
  - - 'aaa'
    - 'bbb'
    - 'ccc'
  - - 'dd'
    - 'ee'
#物品的映射表
source:
  a: 'bedrock'
  b: 'command_block'
  c: 'items:example_item:example_item'
  d: 'diamond'
  e: 'iron_ingot'
#是否在配方书中为玩家解锁此配方，默认为config.yml中的all_recipe_unlocked配置项
unlock: true

#可选的配置项：
#配方合成的条件配置
condition: 'if all perm craftorithm.perm.example && level >= 100 && papi %player_name% == Anisufia'
#配方合成之后执行的动作
actions:
  - 'example'
```
{% endtab %}

{% tab title="无序配方" %}
#### example\_shapeless.yml

```yaml
type: 'shapeless'
result: 'bedrock'
multiple: true
source:
  - - 'bedrock'
    - 'bedrock'
    - 'bedrock'
  - - 'command_block'
    - 'command_block'
    - 'command_block'
```
{% endtab %}

{% tab title="烧炼配方" %}
#### example\_cooking.yml

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

#### example\_random\_cooking.yml

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
  - block: smoking
    item: bedrock
  - block: blasting
    item: bedrock
exp: 10
time: 100
```
{% endtab %}

{% tab title="锻造配方" %}
#### example\_smithing.yml

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
{% endtab %}

{% tab title="切石机配方" %}
#### example\_stone\_cutting.yml

```yaml
type: stone_cutting
result:
  - bedrock
  - diamond
  - iron_ingot
multiple: true
source:
  - command_block
  - bedrock
```
{% endtab %}
{% endtabs %}

## 物品

{% tabs %}
{% tab title="example_item.yml" %}
```yaml
example_item:
  material: STONE_PICKAXE
  amount: 10
  nbt:
    Damage: 78
```
{% endtab %}
{% endtabs %}
