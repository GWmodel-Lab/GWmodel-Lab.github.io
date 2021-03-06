---
title: 低高度飞行安全系数评估会议记录
author: 
  nick: hpdell
  link: https://hpdell.github.io/
date: 2018-07-04 14:26:00
subtitle: 2018年7月4日会议
cover: /img/minhang.jpg
tags:
  - 民航
categories: 会议记录
---
# 低高度飞行安全系数评估

风险系数：

## 整体步骤

1. 探测航段
2. 评估航段安全系数

## 模型

### 模型参数

操纵方面的参数：

1. 速度
2. 高度
3. 下降率
4. 姿态
5. 形态
6. 水平轨迹
7. 垂直轨迹
8. 警告：一旦触发，直接得到模型结果

### 模型变量

#### 因变量

因变量是安全系数，**评估整个航段**，**采用经验值**。
使用不稳定时刻的飞机参数计算。

#### 自变量

自变量是 **触发时刻的** 所有8类模型参数。

### 模型设计

1. 考虑飞机整体情况，综合得到安全系数。
2. 一个指标超标严重，直接得到安全系数。（整合到综合危险系数中）

### 常用模型

1. 机器学习：只能看到输入输出，不能看到中间过程。
2. 回归分析：可以看到中间结果。
3. 判别分析：根据特征矩阵，判断隶属于某种类型的概率。
4. ~~非监督分类：给出所有数据聚类~~

## 要求

### 数据要求

1. 数据量大。
2. 需要有大量因变量确定的样本（1000 个），还有一批没有因变量的测试样本。
3. 样本因变量值最好是经验数值，经验区间次之。
4. 样本的触发条件分布均匀。
5. 降落阶段 200 英尺以下所有不稳定的数据。
6. 数据采样率：1 s。

### 其他要求

1. 事故征候：有以下两点，经检查后如果不能正常起飞，定义为事故征候。
    - 飞机是否受损
    - 人员是否受伤
2. 需要判断的规则文档，记录判断的原因。

## 问题

Q: 如何根据每个参数与因变量的对应关系，得到飞机整体状态与因变量的对应关系？  
A: 先定单因子，再根据单因子及其相关的参数，得到风险系数。

Q: 飞行员无法给出具体的风险系数值。  
A: 采用区间问卷调查的方法，将风险等级分为5级。

## 时间节点

1. 风险系数数据：8月份（一个月）。
2. 一个月 200 英尺以下所有数据：2周（尽快）。