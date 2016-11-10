---
title: Java学习笔记--内部类
date: 2016-11-09 09:48:20
tags:
---
###内部类的构造：
内部类相当于外部类的成员属性。
Outer out=new Outer();
Outer.Inner=out.new Outer();

``` bash 
public class Demo{
	public static void main(String[] args){
		//接口类型(抽象类)不能直接进行实例化
		Outer out=new Outer(){
			@Override
			public void show() {
				System.out.println("匿名内部类的show方法");
			}
		};
		out.show();
		
		Parent p=new Parent(){
			public void work(){
				System.out.println("son is working");
			}
		};
		p.work();
	}
}

//接口
interface Outer{
	public void show();
}
//父类
class Parent{
	public void work(){
		System.out.println("parent is working");
	}
}
```

## 局部内部类
在类的局部位置进行轻易的类。
在局部内部类里面可以访问外部类的成员变量。
局部内部类访问方法中的局部变量的时候，
``` bash
public class Test {
	
}

class ColinL{
	private String name;
	public void work(final int i){
		final int count = 0;
		class In{
			public void inWorking(){
				System.out.println(name);
				System.out.println(i);
				System.out.println(count);
			}
		}
	}
}
```

## 静态内部类
静态内部类中可以申明static成员变量：非静态内部类中不可以
静态内部类不可以使用外部类的非静态成员变量
创建静态内部类的对象，不需要其外部类的对象
``` bash
public class Test {
	static int count=1;
	
		static class Inner{
			public void working(){
				System.out.println(count);
			}
		}
}
```

## 内部类的继承
``` bash
public class Test extends A.B {
	//构造器 
	public Test(A a){
		//构造a
		a.super();
	}
}

class A{
	class B{
		
	}
}
```