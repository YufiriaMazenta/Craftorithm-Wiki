---
description: 一个插件定义的配方应该由哪些配置项构成
---

# 配置构成

## 配方的存储方式

在插件中，所有的配方文件都存储在plugins/Craftorithm/recipes文件夹下，每个文件代表一个配方。配方文件的命名必须符合原版限制，即只包含字母、数字、下划线\_、左斜杠/、负号-，不符合此要求的文件名将不会被注册。

## 公共配置项

所有的配方都有的配置项

<table><thead><tr><th>配置项</th><th>数据类型</th><th>解释</th><th data-type="checkbox">是否必须</th></tr></thead><tbody><tr><td>type</td><td>String</td><td>配方的类型，规定一个配方应该是什么类型的，若没有配置此项，则默认按有序配方进行解析</td><td>false</td></tr><tr><td>result</td><td>String</td><td>配方的结果，除切石机配方外，所有的配方都只能有一种结果</td><td>true</td></tr><tr><td>unlock</td><td>Boolean</td><td>是否自动为玩家在合成之书中解锁此配方，此处配置优先级高于config.yml中的all_recipe_unlocked配置项，若没有配置此项，默认为上述全局配置项</td><td>false</td></tr><tr><td>source</td><td>复杂类型</td><td>配方的合成物品，不同的配方有不同的编写格式</td><td>true</td></tr><tr><td>multiple</td><td>Boolean</td><td>规定此配方是否有多种合成方式，默认为false</td><td>false</td></tr></tbody></table>

## 私有配置项

每种配方独有的配置项，详细请看各配方的编写教程
