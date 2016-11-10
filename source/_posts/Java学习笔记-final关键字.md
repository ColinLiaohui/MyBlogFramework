---
title: Java学习笔记--final关键字
date: 2016-11-08 16:21:20
tags:
---
### 1.final修饰变量
恒定不变的属性，可以使用final在进行修饰。
变量名建议全部使用大写。
final修饰的变量不能改变，如果在程序中重新赋值，编译会报错。
public static final String SKIN_COLOR="yellow";
public static final int EYE_COUNT=2;
public static final String EYE_COLOR="black";


### 2.final修改方法
任何继承类无法覆盖该方法。但是重载不会受到限制。
``` bash
public class Colin {

}
class Tree{
	public final void develop(){
		System.out.println("123");
	}
}
class Oak extends Tree{
	public Oak(){
		System.out.print("456");
	}
	//被final修饰的develop被重载
	public void develop(String name){
		
	}
}
```


### 3.final修饰类名
该类不能作为任何类的父类。
类中的方法会全部被自动定义为final类型。