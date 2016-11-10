---
title: Java学习笔记--抽象类
date: 2016-11-08 17:18:44
tags:
---
## 抽象类
### 抽象类的定义
抽象类是为子类提供与一个规范。
修饰符 abstract 类名{
	//类体
	修饰符 abstract 返回值类型 方法名(参数列表);
}
抽象方法没有方法体：public abstract class Test();
非抽象方法有方法体：public abstract class Test() {
	
	public abstract void test();
}
如果定义一个抽象类，则这个类中至少有一个抽象方法。

### 抽象类的使用
@override  可以用来检测是否重写正确。
1、一个类继承了抽象类，就必须要重写该类的抽象方法。
2、如果有一个类没有重写抽象类的方法，则这个类也要定义为抽象类。