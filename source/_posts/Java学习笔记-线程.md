---
title: Java学习笔记--线程
date: 2016-11-09 14:15:36
tags:
---
## 继承Thread类创建线程
创建方式：
``` bash
class 类名 extends Thread{
	//重写run方法
	public void run(){
		//
	}
}
```

## 实现Runnable接口创建多线程
创建方式：
``` bash
class A implements Runnable{
	public void run(){

	}
}
//调用
A a = new A();
Thread t = new Thread(a);
a.star();
```
例：
``` bash
//线程1
public class MyRunnable1 implements Runnable {

	@Override
	public void run() {
		// TODO Auto-generated method stub
		for(int i=0;i<100;i++){
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			System.out.println("*");
		}
	}
	
}
//线程2
public class MyRunnable2 implements Runnable {

	@Override
	public void run() {
		// TODO Auto-generated method stub
		for(int i=0;i<100;i++){
			try {
				Thread.sleep(1000);
			} catch (InterruptedException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			System.out.println("&");
		}
	}
}
//启动线程
public class Test {
	public static void main(String[] argd){
		MyRunnable1 r1=new MyRunnable1();
		MyRunnable2 r2=new MyRunnable2();

		//设置优先级 最高10 最低1
		t1.setPriority(Thread.MAX_PRIORITY);
		t2.setPriority(Thread.MIN_PRIORITY);
		System.out.println(t1.getPriority());
		System.out.println(t2.getPriority());

		Thread t1=new Thread(r1);
		Thread t2=new Thread(r2);
		t1.start();
		t2.start();
	}
}
```