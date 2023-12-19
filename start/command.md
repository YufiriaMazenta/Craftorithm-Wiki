---
description: 插件的命令解释
---

# 命令

## 命令结构

* /craftorithm | /craft
  * item
    * save
    * give
  * reload
  * remove
  * version
  * run
  * list
  * create
  * disable

## 详细说明

{% hint style="info" %}
在此文中，尖括号"<"、">"包含的参数为必须参数，方括号"\["、"]"包含的参数为可选参数
{% endhint %}

```
/craft item save <namespace> <item_name>
权限：craftorithm.command.item
例：/craft item save example_item test_save
```

* 用途：将手上的物品保存到配置文件中
* 参数详解
  * \<namespace>为物品的命名空间，一般情况下为保存到的配置文件名，若此文件不存在，将会创建新文件
  * \<item\_name>为保存物品的名字

```
/craft item give <namespace>:<item_name> [player_name]
权限：craftorithm.command.item
例：/craft item give example_item:example_item YufiriaMazenta
```

* 用途：获取插件保存的物品
* 参数详解
  * \<namespace>为物品的命名空间，一般情况下为物品所在的配置文件名
  * \<item\_name>为物品的名字
  * \[player\_name]为给予的玩家名字，可选项，如果没有此参数，则默认给予命令执行者

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

```
/craft list [craftorithm/server]
权限：craftorithm.command.list
例：/craft list
```

* 用途：查看新增配方列表/查看服务器现有配方
* 参数详解

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
