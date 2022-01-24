---
layout: post
title: Scalable Distributed Stream Processing
category: /cs/system/stream-based-system
date: Sun Jan 23 2022 22:59:28 GMT-0500
icon: www
tags: distributed, system, 论文小结
image: 1.jpg
preview: 1
---
* Stream-based applications的特征：
	1. 处理海量数据流
	2. 实时响应
	3. 系统外部生成数据，推入系统
 * 数据流的特征：
	 1. 持续到达系统
	 2. 一般会有时间戳
	 3. 是系统外部数据，系统不能控制
	 4. 系统不知道数据的长度，数据可能甚至是无边界的
  * 流处理的主要挑战
    1. 时间
		1. 1分钟如何定义
		2. 时间到达无序怎么办
		3. 设备断连怎么办
		eg. 在森林中不同的地方布置了1000个温度传感器，检测气温和烟雾等级，每5秒生成一次数据。写一个程序，每分钟输出过去十分钟的平均气温。
		* 如何储存数据
		* 怎么判断时间
		* 传感器断连怎么办
    2. 波动的workload
    3. 容错