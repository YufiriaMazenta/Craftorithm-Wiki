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
  * look

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
  * \[player\_name]为给予的玩家名字，可选项，如果没有此参数，则默认给予命令执行者cod

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
/craft remove <recipe_key>
权限：craftorithm.command.remove
例：/craft remove craftorithm:example_shaped
```

* 用途：删除指定Key的配方
* 参数详解
  * \<recipe\_key>为配方的key。格式为"\<namespace>:\<name>"，一般情况下，原版配方的命名空间是"minecraft"，而插件添加的配方的命名空间为插件名字的全小写。本插件添加的配方的\<name>一般为配方文件的文件名。

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
/craft look [recipe_key]
权限：craftorithm.command.look
例：/craft look craftorithm:example_shaped
```

* 用途：查看配方列表/单独查看某配方
* 参数详解
  * \[recipe\_key]为配方的key。格式为"\<namespace>:\<name>"，一般情况下，原版配方的命名空间是"minecraft"，而插件添加的配方的命名空间为插件名字的全小写。本插件添加的配方的\<name>一般为配方文件的文件名。
