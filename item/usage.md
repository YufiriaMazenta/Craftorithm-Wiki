# 物品的保存与使用

## 保存物品

插件使用命令`/craft item save <namespace> <item_name>`将物品保存到配置文件中。详细说明请看[命令](../start/command.md#xiang-xi-shuo-ming)。

## 使用物品

### 获取物品

玩家可以使用命令`/craft item give <namespace>:<item_name> [player_name]`获取物品的实例。详细说明请看[命令](../start/command.md#xiang-xi-shuo-ming)。

### 在配方文件中使用物品

在配方文件中，玩家可以以格式`items:<namespace>:<item_name>`使用插件保存的物品。例如`items:example_item:example_item`。

另外，也可以使用格式`items:<namspace>:<item_name> <amount>`，此格式会改变物品的数量，最终数量为物品本身定义的数量乘\<amount>的结果。

{% hint style="info" %}
注意：除了铁砧配方之外，其他配方的物品数量都只在作为结果时有效。即无论物品有多少个，配方中需求的物品数量都为1。
{% endhint %}
