---
description: 插件的命令解释
---

# 命令和权限

## 命令结构

* /craftorithm | /craft | /cra
  * item
    * save
    * give
    * fuel
      * add
      * remove
  * reload
  * remove
  * version
  * run
  * list
    * server
    * craftorithm
  * create
  * disable
  * display

## 权限表

<table><thead><tr><th width="339">权限</th><th>作用</th><th width="100" align="center">默认</th></tr></thead><tbody><tr><td>craftorithm.command</td><td>使用命令/craftorithm | /craft | /cra</td><td align="center">op</td></tr><tr><td>craftorithm.command.item</td><td>使用命令/cra item</td><td align="center">op</td></tr><tr><td>craftorithm.command.item.give</td><td>使用命令/cra item give</td><td align="center">op</td></tr><tr><td>craftorithm.command.item.save</td><td>使用命令/cra item save</td><td align="center">op</td></tr><tr><td>craftorithm.command.item.fuel</td><td>使用命令/cra item fuel</td><td align="center">op</td></tr><tr><td>craftorithm.command.item.fuel.remove</td><td>使用命令/cra item fuel remove</td><td align="center">op</td></tr><tr><td>craftorithm.command.item.fuel.add</td><td>使用命令/cra item fuel add</td><td align="center">op</td></tr><tr><td>craftorithm.command.create</td><td>使用命令/cra create</td><td align="center">op</td></tr><tr><td>craftorithm.command.disable</td><td>使用命令/cra disable</td><td align="center">op</td></tr><tr><td>craftorithm.command.list</td><td>使用命令/cra list</td><td align="center">op</td></tr><tr><td>craftorithm.command.list.server</td><td>使用命令/cra list server</td><td align="center">op</td></tr><tr><td>craftorithm.command.list.craftorithm</td><td>使用命令/cra list craftorithm</td><td align="center">op</td></tr><tr><td>craftorithm.command.remove</td><td>使用命令/cra remove</td><td align="center">op</td></tr><tr><td>craftorithm.command.reload</td><td>使用命令/cra reload</td><td align="center">op</td></tr><tr><td>craftorithm.command.run</td><td>使用命令/cra run</td><td align="center">op</td></tr><tr><td>craftorithm.command.version</td><td>使用命令/cra version</td><td align="center">op</td></tr><tr><td>craftorithm.command.display</td><td>使用命令/cra display</td><td align="center">op</td></tr><tr><td>craftorithm.edit_recipe</td><td>进入配方编辑页面</td><td align="center">op</td></tr></tbody></table>

{% hint style="info" %}
由于/cra list命令在没有参数的情况下默认执行/cra list craftorithm，所以需要craftorithm.command.list和craftorithm.command.list.craftorithm两个权限才能正常使用/cra list命令
{% endhint %}

## 详细说明

{% hint style="info" %}
在此文中，尖括号"<"、">"包含的参数为必须参数，方括号"\["、"]"包含的参数为可选参数
{% endhint %}

{% hint style="info" %}
所有命令都需要有craftorithm.command权限才能使用
{% endhint %}

<pre><code><strong>/craft item save &#x3C;namespace> &#x3C;item_name>
</strong>权限：craftorithm.command.item和craftorithm.command.item.save
例：/craft item save example_item test_save
</code></pre>

* 用途：将手上的物品保存到配置文件中
* 参数详解
  * \<namespace>为物品的命名空间，一般情况下为保存到的配置文件名，若此文件不存在，将会创建新文件
  * \<item\_name>为保存物品的名字

```
/craft item give <namespace>:<item_name> [player_name]
权限：craftorithm.command.item和craftorithm.command.item.give
例：/craft item give example_item:example_item YufiriaMazenta
```

* 用途：获取插件保存的物品
* 参数详解
  * \<namespace>为物品的命名空间，一般情况下为物品所在的配置文件名
  * \<item\_name>为物品的名字
  * \[player\_name]为给予的玩家名字，可选项，如果没有此参数，则默认给予命令执行者

```
/craft item fuel add <time>
权限：craftorithm.command.item.fuel和craftorithm.command.item.fuel.add
```

* 用途：添加一个自定义燃料
* 参数详解
  * \<time>是此燃料可烧炼的时间，单位为tick，20tick等于一秒

```
/craft item fuel remove <name>
权限：craftorithm.command.item.fuel和craftorithm.command.item.fuel.remove
```

* 用途：删除一个自定义燃料
* 参数详解
  * \<name>是自定义燃料的名字

```
/craft reload
权限：craftorithm.command.reload
```

* 用途：重载插件的配置文件
* 重载内容
  * items文件夹中的所有物品
  * recipes文件夹中的所有配方
  * function.yml定义的所有函数
  * config.yml中的所有配置项
  * lang.yml中的所有配置项

```
/craft remove <recipe_name>
权限：craftorithm.command.remove
例：/craft remove example_shaped
```

* 用途：删除指定的配方组
* 参数详解
  * 此命令只能用于删除Craftorithm新增的配方。recipe\_name即为你添加配方时的名字

```
/craft version
权限：craftorithm.command.version
```

* 用途：查看当前运行的插件版本

```
/craft run <action_line>
权限：craftorithm.command.run
例：/craft run example
```

* 用途：运行一条插件的动作语句
* 参数详解
  * \<action\_line>为一条动作语句，中间可以使用空格

<pre><code>/craft list [craftorithm/server]
<strong>权限：craftorithm.command.list和
</strong><strong>craftorithm.command.list.craftorithm或craftorithm.command.list.server
</strong>例：/craft list
</code></pre>

* 用途：查看新增配方列表/查看服务器现有配方
* 参数详解
  * 当不填写参数时，默认执行参数为craftorithm的子命令

<pre><code><strong>/craft create &#x3C;recipe_type> &#x3C;recipe_name>
</strong>权限：craftorithm.command.create
例：/craft create shaped test/shaped
</code></pre>

* 用途：通过GUI在游戏内添加配方
* 参数详解：
  * \<recipe\_type>为配方类型，目前支持通过GUI创建的配方有“有序(shaped)”、“无序(shapeless)”、“烧炼(cooking)”、“锻造(smithing)”、“切石(stone\_cutting)”这些。
  * \<recipe\_name>为配方名字，只支持小写英文字母、数字、"\_"、"/"、"."、"-"。

```
/craft disable <recipe_key>
```

* 用途：禁用原版或其他插件的配方
* 参数详解：
  * \<recipe\_key>为配方的key。格式为"\<namespace>:\<name>"，一般情况下，原版配方的命名空间是"minecraft"，而插件添加的配方的命名空间为插件名字的全小写。

```
/craft display <recipe_key>
```

* 用途：打开查看配方合成方式的GUI
* 参数详解：
  * \<recipe\_key>为配方的key。格式为"\<namespace>:\<name>"，一般情况下，原版配方的命名空间是"minecraft"，而插件添加的配方的命名空间为插件名字的全小写。
