# 基于Python的开源云原生Web应用级防火墙(WAF)实现

Author: *ZHENG Hai-Lin*, *Ich1ka_chan(FAN CZ)*, *ZHAN Yi-Xuan*, *ZHONG Jun-Hao*, *Huang Yao-Kun*

## Introduction：
随着互联网的迅猛发展，Web应用的安全问题日益凸显。Web应用级防火墙（Web Application Firewall）作为一种专门用于保护Web应用的安全工具，已经成为企业网络安全架构中不可或缺的一部分。本项目将详细介绍如何基于Python开发一款开源的云原生Web应用防火墙，并提供详细的实现过程。

## Direction: 
**WAF基础知识:**
- 什么是WAF
- WAF的工作原理
- WAF的主要功能
- 技术选型

**环境搭建：**
- Python环境配置
- 必要的依赖库安装
- Docker容器化部署
- 核心功能实现

**实现过程:**
- 请求拦截与过滤
- 攻击检测与防御
- 日志记录与告警
- 高级功能扩展

**自定义规则引擎:**
- 集成外部威胁情报
- 高可用与负载均衡
- 实战案例

**部署与配置:**
- 攻击模拟与防护效果验证
- 性能优化与调优
- 总结与展望

## 一、WAF基础知识
**Descrption:**
WAF（Web Application Firewall）即Web应用防火墙，是一种专门保护`Web`应用程序的安全设备或软件。它通过监测、过滤和阻止来自 Web 应用层的恶意流量（如 SQL 注入、XSS 攻击、CSRF 等），为网站和 Web 服务提供针对性的安全防护。

## 二、WAF功能
以下列举了`WAF`部分核心功能
1.**防注入攻击：**
- 检测并拦截 SQL 注入、命令注入、LDAP 注入等攻击。例如：拦截包含' OR 1=1 --等恶意 SQL 语句的请求。
2.**防跨站脚本（XSS）：**
- 过滤包含恶意 JavaScript 代码的请求或响应。例如：阻止<script>alert('XSS')</script>类型的攻击。
3.**防 CSRF 攻击：**
- 验证请求来源，防止跨站请求伪造。
4.**访问控制：**
- 基于 IP(如CDN)、地理位置、用户代理（User-Agent）等限制访问。例如：封禁频繁访问的恶意 IP。
5.**协议合规性检查**
- 验证 HTTP 请求是否符合规范，阻止异常请求。
