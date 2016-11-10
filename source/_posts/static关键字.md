---
title: Java学习笔记--static关键字
date: 2016-11-08 15:55:15
tags:
---
### 1.静态变量
静态变量是属于类的，和对象没有关系。非静态变量是属于某个对象的，每个对象都有该数据的副本，静态变量只有一个。
访问静态变量是通过（类名.变量名）来访问的
``` bash
public class Colin {

	int commonint = 0;//普通变量
	static int staticint = 0;//静态变量
	
	Colin(int x){
		this.commonint = x;
	}
	
	public static void main(String[] args){
		Colin c1 = new Colin(1);
		Colin c2 = new Colin(2);
		//打印结果
		//c1.commonint:1
		//c1.commonint:2
		c1.staticint = 1;
		//c1.commonint:1
		//c1.commonint:1
		c2.staticint = 20;
		//c1.commonint:20
		//c1.commonint:20
	}
}
```

### 2.静态方法
用static修饰的方法。
访问静态方法是通过（类名.方法名）来调用的。
注：1.静态方法不能访问非静态变量；2.非静态方法可以访问静态变量
生命周期：静态属性或方法是在类加载的时候产生的。非静态的属性或方法是在new的时候产生的。
``` bash
public class Colin {

	public static void main(String[] args){
		ColinMethod.printString("colin");
	}
}

class ColinMethod{
	static void printString(String str){
		System.out.println(str);
	}
}
````

### 3.静态常量
定义例子：public static final int x=123;
```  bash
public class Colin {

	static int x=0;
	static{
		x=100;
	}
	Colin(){
		System.out.println(x);
		//打印结果：100
	}
	public static void main(String[] args){
		new Colin();
	}
}
```