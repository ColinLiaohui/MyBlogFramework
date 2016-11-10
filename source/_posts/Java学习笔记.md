---
title: Java学习笔记--方法
date: 2016-11-08 15:02:04
tags:
---

## 构造方法
用于初始化参数。所有的数字变量全部设置为0，所有的boolean类型全部设置为false，所有的对象类型全部设置为null。
###设计自己的构造方法：
1.方法名和类名相同；
2.没有返回值
注：如果实现了有参的构造方法，系统不再自动提供无参的构造方法，必须自己实现。

``` bash
public class Colin {

	String name;
	String sex;
	int age;
	
	//无参构造方法
	Colin(){
		name = null;
		sex = null;
		age = 0;
	}
	//有参构造方法
	Colin(String name, String sex, int age){
		this.name=name;
		this.sex=sex;
		this.age=age;
	}
	
	public static void main(String[] args){
		//有参数
		Colin c = new Colin();
		//无参数
		Colin co = new Colin("colin","man",25);
	}
}
```

## 方法的重载
在同一个类中可以有多个方法共享同一个名称，只要他们的参数不一样就行。
根据参数类型和参数数量来决定要调用的方法。
重载：具有相同的方法名称，不同的参数列表。
不同的参数列表指的是：参数类型不同、参数数量不同、参数顺序不同。
```bash
public class Colining {
	public String study(String name){
		String username = name;
		return username;
	}
	public String study(){
		return "colin";
	}
}
```

