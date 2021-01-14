# 初识Soul

------

## 本节概述

- 初步认识 Soul

## 主要内容

### 什么是Soul？

Soul （High Performance API Gateway） 是一个异步的，高性能的，跨语言的，响应式的 API 网关。创始人[肖宇](https://github.com/yu199195)希望能够有一样东西像灵魂一样，保护您的微服务。参考了 Kong ，Spring-Cloud-Gateway 等优秀的网关后，站在巨人的肩膀上，Soul 由此诞生！

### 项目相关地址

- Github:https://github.com/dromara/soul

- Docs:https://dromara.org/zh-cn/docs/soul/soul.html

### 项目特点

- 支持各种语言（http协议），支持 dubbo，springcloud协议。

- 插件化设计思想，插件热插拔，易扩展。

- 灵活的流量筛选，能满足各种流量控制。

- 内置丰富的插件支持，鉴权，限流，熔断，防火墙等等。

- 流量配置动态化，性能极高，网关消耗在 1~2ms。

- 支持集群部署，支持 A/B Test，蓝绿发布。

### 项目架构图

![img](picture/%E5%88%9D%E8%AF%86Soul/soul-framework-20210114190534918.png)

## 知识拓展

### 相关文章推荐

- [认识 API 网关](http://www.iocoder.cn/Fight/This-article-takes-you-through-the-API-gateway-from-entry-to-abandonment/?self)

### 知识点拓展

1. 想要了解 Soul ，肯定先要了解网关，那什么是网关？网关作为流量入口，转发所有用户的请求给后端服务器，同时可以针对流量做一些扩展，比如鉴权、限流、权限、熔断、协议转换、错误码统一、缓存、日志、监控、告警等，目的是使业务方能够更专注于业务逻辑。