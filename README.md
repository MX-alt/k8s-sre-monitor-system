# K8s Full-Stack System Monitoring Dashboard

本项目是一个基于 Kubernetes 的全栈监控演示系统，模拟了从硬件采集到前端展示的完整链路。

## 🏗 架构说明
- **Backend**: 使用 Go 语言编写，实时采集容器磁盘占用并暴露 `/api/disk` 接口。
- **Frontend**: Nginx 容器提供静态 Web 页面，并作为反向代理 (Reverse Proxy) 转发数据。
- **K8s Orchestration**: 
  - 通过 `Service` 实现内部服务发现。
  - 通过 `ConfigMap` 实现 Nginx 代理路径的动态配置。
  - 通过 `Labels/Selectors` 实现流量精准路由。

## 🚀 核心技术点
- **标签排障**: 解决了微服务间的标签冲突与流量重叠问题。
- **性能压测**: 通过 `kubectl exec` 注入磁盘压力，验证监控系统的实时响应。
- **自动化监控**: 前端通过 Polling 机制实现监控指标的自动刷新。

## 📸 项目演示
访问 8080 端口可查看蓝色实时监控进度条。