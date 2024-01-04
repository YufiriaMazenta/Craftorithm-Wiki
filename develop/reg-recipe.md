---
description: 通过Craftorithm的配方系统注册配方
---

# 注册配方

要通过Craftorithm的配方系统注册配方，首先需要注册一个配方组（com.github.yufiriamazenta.craftorithm.recipe.RecipeGroup），配方组类的构造函数最少需要三个参数，分别为配方组名字，配方组的配方类型，配方组的配置文件。使用`com.github.yufiriamazenta.craftorithm.recipe.RecipeManager`提供的addRecipeGroup方法进行注册。

注册完配方组后，可以使用对应类型的RecipeRegistry类进行配方注册，需要注意的是，RecipeRegistry的group参数必须和你注册的配方组名字相同，且一个配方组只能有一种类型的配方，否则将无法正常加载配方；RecipeRegistry使用register方法进行注册。

此外，你还可以直接使用\``com.github.yufiriamazenta.craftorithm.recipe.RecipeManager`提供的loadRecipeGroup方法自动从配方组的配置文件读取并注册配方组。

#### 简略说明一下注册流程：

1. 构造配方组对象
2. 使用RecipeManager.addRecipeGroup注册配方组
3. 构造配方对象
4. 使用register方法注册配方

或

1. 构造配方组对象
2. 使用RecipeManager.loadRecipeGroup自动注册配方组和配方
