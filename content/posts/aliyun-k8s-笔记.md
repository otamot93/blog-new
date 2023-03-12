---
title: "Aliyun K8s 笔记"
date: 2023-03-11T13:00:14+08:00
draft: false
---

## Pod

### 多业务容器使用场景
- web容器(tomcat、openresty)与多个业务程序（war包、或node程序）都存在单独维护的情况下，独立打包，但通过同一个web服务暴露(微服务场景下较少使用)
- sidecar 解耦与复用:日志收集、监控、通用shell脚本、集群代理（客户端负载均衡，istio）、接口适配器容器等 


### 需要解决的问题
#### 实现网络共享
通过infra容器(pause容器),其他业务容器通过--net=container:pause

#### 实现存储共享
volume映射相同卷

### pod网络


## 应用编排
- Deployment 管理部署发布的控制器

### Deployment
创建ReplicaSet，由一个ReplicaSet管理一个版本的pod
功能:
- Controller会维护pod数量与期望数量一直
- 更新策略
- 回滚



