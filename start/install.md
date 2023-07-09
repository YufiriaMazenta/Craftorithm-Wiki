---
description: 如何将本插件安装到服务器
---

# 安装

## 需求

1.13-1.20.1的Spigot及其分支服务端

## 版本号的说明

通常情况下，插件的版本号为a.b.c-xxx格式，a为大版本号，一般只有重构插件时才会变动；当有新功能增加时，通常b会变动；而c的变动一般是BUG修复。xxx一般为dev、beta等特殊版本。

## 下载

1. 从Github Releases下载本插件的最新发布版（推荐）
2. 从MCBBS下载本插件的最新发布版
3. 从Github Actions下载本插件的构建版

{% embed url="https://github.com/YufiriaMazenta/Craftorithm/releases" %}
从Gihub Releases下载
{% endembed %}

{% embed url="https://beta.mcbbs.net/resource/servermod/msgmko78/releases" %}
从MCBBS v4下载
{% endembed %}

{% embed url="https://github.com/YufiriaMazenta/Craftorithm/actions" %}
从Github Actions下载
{% endembed %}

{% hint style="info" %}
注意：在Github Actions中，分为正式版、beta版和dev版三种版本，其中dev版为开发过程中版本，可能会存在未完成的功能；beta版为测试版，通常功能是完成的，但未经严格测试；正式版和发行版本无差别。
{% endhint %}

## 安装

1. 从以上链接下载本插件
2. 对于1.4.0及以上版本的插件，还需要安装前置插件ParettiaLib，下载链接[https://github.com/YufiriaMazenta/ParettiaLib/actions](https://github.com/YufiriaMazenta/ParettiaLib/actions)
3. 将其放入服务端的plugins目录
4. 重启服务端

## 从0.2.x版本OasisRecipe迁移到本插件

1. 删除原OasisRecipe插件jar文件
2. 将Craftorithm和OasisRecipeUpdater插件放入plugins文件夹
3. 重启服务端
4. 输入命令/oru
5. 迁移完成

{% hint style="info" %}
注意：暂不支持迁移0.2.x版本的随机烧炼配方，如有需要请自行迁移。
{% endhint %}
