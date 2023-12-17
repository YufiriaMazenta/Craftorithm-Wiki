---
description: 插件对多语言的支持
---

# 本地化

在1.7.0以上版本，Craftorithm内置多语言模块，会自动根据玩家的语言显示、发送对应的文本，插件预设了简体中文、繁体中文（台湾）、繁体中文（香港）、英语（US）、德语、日语、俄语的翻译文件。

如果你需要新增一个语言，只需要在lang文件夹下创建名为“语言代码.yml”的翻译文件即可。

需要注意，语言文件与minecraft自身的语言代码格式相同，为全小写格式，使用下划线“\_”分割。例如：简体中文（zh-CN）的文件名应为zh\_cn.yml，而美国英语（en-US）的文件名应为en\_us.yml。具体语言代码可参考如下链接。

{% embed url="https://zh.minecraft.wiki/w/%E8%AF%AD%E8%A8%80" %}
中文MCWIKI
{% endembed %}

{% embed url="https://minecraft.wiki/w/Language" %}
英文MCWIKI
{% endembed %}

而在1.7.0之前，插件只提供一个lang.yml的语言文件，无法根据玩家语言显示文本。
