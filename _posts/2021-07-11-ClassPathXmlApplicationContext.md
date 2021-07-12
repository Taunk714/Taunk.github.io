---
layout: post
title: 2021-07-11-ClassPathXmlApplicationContext
category: spring
date: Sun Jul 11 2021 20:38:14 GMT+0800
icon: www
keywords: spring
image: 1.jpg
preview: 1
---
源码
```java
public class ClassPathXmlApplicationContext extends AbstractXmlApplicationContext {

	@Nullable
	private Resource[] configResources;

	// 省略了非常多的Constructor，总之最后都是调用下面这个Constructor
	
	public ClassPathXmlApplicationContext(
		String[] configLocations, boolean refresh, @Nullable ApplicationContext parent)
		throws BeansException {

		super(parent);
		// 调用setConfigLocations方法解析文件名
		// 1. 检查xml配置路径是否为null，null报错。
		// 2. 替换路径中的占位符
		setConfigLocations(configLocations); 
		
		
		if (refresh) {
			refresh();
		}
	}
	
	// 省略一个get方法
}
```