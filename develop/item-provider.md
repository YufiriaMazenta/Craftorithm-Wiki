---
description: 物品提供者用于Craftorithm获取你提供的物品
---

# 物品提供者

Craftorithm的物品系统暴露了一个名为ItemProvider的接口，通过此接口，你可以让Craftorithm读取你的插件提供的物品，而可以做到在你的NBT有变动的情况下可以自动更新配方的物品。效果如下：

{% embed url="https://yufiriamazenta.gitbook.io/craftorithm-wiki/recipe/user-other-plugins-item" %}

插件内置了Craftorithm、ItemsAdder、MMOItems、MythicMobs、NeigeItems和Oraxen的物品提供者，可参考实现。

### 使用方式

首先，你需要有一个实现`com.github.yufiriamazenta.craftorithm.item.ItemProvider`接口的类，此接口需要实现三个方法，分别为namespace()、getItemName()和getItem()。

namespace方法需要返回你的物品提供类的命名空间。对于相同命名空间的物品提供者，后注册者将会覆盖先注册者。

getItemName方法接受两个参数，一个是ItemStack，一个是boolean，前者是用于匹配的物品，而后者用于标识是否忽略物品数量。对于不忽略物品数量的情况，你需要返回“物品名字 数量”这样的标识，否则将会出现合成结果与设置时不符的情况。

getItem方法接受一个参数，为String类型，其为物品的名字，此方法无需处理物品的数量问题，只需要按照名字返回物品即可。

实现完接口后，你还需要手动注册物品提供者，使用`com.github.yufiriamazenta.craftorithm.item.ItemManager`提供的regProvider方法即可注册。

此时，插件将可以使用`命名空间:id`的格式来读取你的物品，同时使用GUI创建配方时也能够自动识别到你的物品ID。
