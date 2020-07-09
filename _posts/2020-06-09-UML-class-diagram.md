---
layout: post
title: UML 类图
description: UML中的类图介绍
modified: 
tags: [OOP]
readtimes: 5
published: true
image:
  feature: 
  background: 
---

> 统一建模语言（英语：Unified Modeling Language，缩写 UML）是非专利的第三代建模和规约语言。UML是一种开放的方法，用于说明、可视化、构建和编写一个正在开发的、面向对象的、软件密集系统的制品的开放方法。UML展现了一系列最佳工程实践，这些最佳实践在对大规模，复杂系统进行建模方面，特别是在软件架构层次已经被验证有效。

以上是维基百科上对UML的定义，它定义了很多的图，本文主要介绍类图，是属于结构性图形中的静态图，本文所有图是通过OmniGraffle画的。

**结构性图形**（Structure diagrams）强调的是系统式的建模：

+ 静态图（static diagram）
  - 类图
  - 对象图
  - 包图
+ 实现图（implementation diagram）
  - 组件图
  - 部署图
+ 剖面图
+ 复合结构图


**行为式图形**（Behavior diagrams）强调系统模型中触发的事件：

+ 活动图
+ 状态图
+ 用例图

**交互性图形**（Interaction diagrams），属于行为图形的子集合，强调系统模型中的资料流程：

+ 通信图
+ 交互概述图（UML 2.0）
+ 时序图（UML 2.0）
+ 时间图（UML 2.0）

## 定义

UML类图是描述类的内部结构（属性, 方法等）和类与类之间的关系（泛化, 实现，组合, 聚合，关联，依赖），是一种静态结构图。是在面向对象程序设计中建模的常用方法，不仅是系统编码和测试的重要模型，以图的形式展示还可以简化人们对系统的理解。

## 格式

一般是用三层矩形框表示，第一层表示类的名称，第二层表示的是字段和属性，第三层则是类的方法，如果某一层没有则可以省略。第一层中，如果是**抽象类**，名称需用*斜体*显示。

![class](https://img.fythonfang.com/20200708115611873_1519558387.jpg)

属性和方法前面的符号（+、#、-等）代表可见性

- Public(`+`)
- Protected(`#`)
- Private(`-`)
- Package(`~`)

第二层属性的格式是

> 可见性 名称 : 类型 [= 默认值]

第三层方法的格式是

> 可见性 名称(参数类型 参数, ...) : 返回类型

## 类与类之间的关系

类图中类与类之间的关系主要由：继承、实现、依赖、关联、聚合、组合这六大类型。表示方式如下图：

![relation](https://img.fythonfang.com/20200708115205255_1705085089.jpg)

### 泛化（generalization/extens）

泛化又称继承，是IS-A的关系，两个对象之间如果可以用IS-A来表示，就是继承关系：（..是..)

泛化关系用一条带空心箭头的实线表示；如下图表示（猫继承自动物）猫是（IS-A）动物

![generalization](https://img.fythonfang.com/20200708154854835_905887702.jpg)

### 实现（realization/implements)

实现关系指的是一个class类实现interface接口（可以是多个）的功能，在Java中可以直接用关键字`implements`表示，在C++中目标类可用抽象类表示

实现关系用一条带空心箭头的虚线表示；如下图自行车必须实现车这个抽象类 注意这个*车*类是斜体代表抽象类

![realization](https://img.fythonfang.com/20200708143201877_1118780767.jpg)

各种关系的强弱顺序： 泛化 = 实现 > 组合 > 聚合 > 关联 > 依赖

### 聚合（aggregation）

聚合关系是整体与部分的关系即HAS-A关系，整体和部分不是强依赖的可以单独存在，此时整体与部分之间是可分离的，他们可以具有各自的生命周期，部分可以属于多个整体对象，也可以为多个整体对象共享，例如公司的部门和员工，即使公司不存在了员工还是存在的。

聚合关系用一条带空心菱形箭头的实线表示，如下所示部门HAS-A员工

![aggregation](https://img.fythonfang.com/20200708152257471_1964177444.jpg)


### 组合（composition）

组合关系也是整体与部分的关系，但部分不能离开整体而单独存在，整体的生命周期结束也就意味着部分的生命周期结束，他体现的是一种CONTAINS-A的关系。如公司和部门是整体和部分的关系，没有公司就不存在部门。组合关系是一种比聚合更强的关系。

组合关系用一条带实心菱形箭头的实线表示，如下表示公司CONTAINS-A部门

![compositon](https://img.fythonfang.com/20200708160550075_2023419750.jpg)

### 依赖（dependency）

依赖关系是一种临时性的关系，通常在运行期间产生，并且随着运行时的变化，可以简单的理解，就是一个类A使用到了另一个类B，而这种使用关系是具有偶然性的、临时性的、非常弱的，但是B类的变化会影响到A。例如程序员依赖电脑工作。

依赖关系是用一条带箭头的虚线表示，依赖有方向如下程序员依赖电脑，也可以是双向的把箭头去掉，双向依赖是一种非常糟糕的结构，我们总是应该保持单向依赖，杜绝双向依赖的产生

![dependency](https://img.fythonfang.com/20200708170807060_288930146.jpg)

### 关联（association）

关联关系是两个类语义级别的一种强依赖关系，这种关系比依赖更强、不存在依赖关系的偶然性、关系也不是临时性的，一般是长期性的，而且双方的关系一般是平等的、关联可以是单向、双向的；表现在代码层面，为被关联类B以类属性或方法的形式出现在关联类A中，也可能是关联类A引用了一个类型为被关联类B的全局变量；

关联关系是用一条带箭头的实线线表示，如下Person和Cat就是关联关系

![association](https://img.fythonfang.com/20200708180808142_129252726.jpg)


## 实例

下面看一个实例

![example](https://img.fythonfang.com/20200709115404034_1447009589.jpg)

1. Dog和Animal是泛化（继承）关系
2. Dog和Person是关联关系，Dog的主人是Person，他们是长期的关系
3. Bike和Vehicle是实现关系，Vehicle是斜体表示abstract
4. Person和Bike是依赖关系，Person依赖Bike是非常弱的关系
5. School和Class是组合关系，班级离不开学校
6. Person和Class是聚合关系，学生和班级是互相独立的

## Reference

1. [zh.wikipedia.org](https://zh.wikipedia.org/wiki/%E7%BB%9F%E4%B8%80%E5%BB%BA%E6%A8%A1%E8%AF%AD%E8%A8%80)
2. [juejin.im](https://juejin.im/post/5d318b485188255957377ac3)
3. [design-patterns.readthedocs.io](https://design-patterns.readthedocs.io/zh_CN/latest/read_uml.html)
