![定义与要素](doc/concept_and_elements.png)

![技术栈](doc/stack.png)

![Landscpae](doc/landscape.png)

![](doc/all.jpg)

---

# Cloud Native

​		云原生既包含技术（微服务，敏捷基础设施），也包含管理（DevOps，持续交付，康威定律，重组等）。云原生也可以说是一系列云技术、企业管理方法的集合。

## 一. Microservice微服务

### 1. 微服务本质

> In short, the microservice architectural style [[1\]](https://martinfowler.com/articles/microservices.html#footnote-etymology) is an approach to developing a single application as a suite of **small** services, each running in its own process and communicating with lightweight mechanisms, often an HTTP resource API. These services are built around business capabilities and **independently deployable** by **fully automated deployment** machinery. There is a bare minimum of centralized management of these services, which may be written in different programming languages and use different data storage technologies.                                                                                                        -   摘自: Martin Fowler的[microservices](http://martinfowler.com/articles/microservices.html)
>
> 
>
> 简单来说，微服务架构风格是一种将一个单一应用程序开发为一组**小型**服务的方法，每个服务运行在自己的进程中，服务间通信采用轻量级通信机制(通常用HTTP资源API)。这些服务围绕业务能力构建并且可通过**全自动部署**机制**独立部署**。这些服务共用一个最小型的集中式的管理，服务可用不同的语言开发，使用不同的数据存储技术。                  - 摘自: YYGCui‘s Blog [微服务](http://blog.cuicc.com/blog/2015/07/22/microservices/#进化式设计)

### 2. 常用框架

#### Spring Cloud框架
> 
> 

#### Dubbo框架

> ![](microservice/dubbo-framework.jpg)
> 摘自: https://dubbo.apache.org/zh/docs/v2.7/dev/design/
> 

### 微服务2.0时代 - ServiceMesh

​		服务网格作为云原生网络基础设施，负责服务间通信的一切方面。


### 3. 基础服务
#### 3.1 API网关服务

> ![](microservice/有关Nginx_OpenResty.png)

##### 3.1.1 基本服务

- Web服务器
  - http服务器
  - https服务器
  - http2服务器
  - http3服务器
  - websocket服务器
- 正向代理
- 反向代理
  - http/https协议
  - tcp协议
  - fastcgi协议
  - websocket协议
- 动静分离
- 负载均衡
  - 加权轮询
  - 源IP散列
  - 响应时间
  - URL散列
- 主备容灾
- 缓存服务
- 动态限流
- 流量路由
- 命名空间限制
- 上游探针
- 认证方式
  - basic auth
- 流量分配
- 请求跟踪
  - trace
- 其他

##### 3.1.2 Nginx

###### 1) nginx架构

![](microservice/ngxin_architecture.png)

###### 2) 基本功能及配置

- 全局配置(基本配置)

  ```nginx
  user                 www-data;
  pid                  /run/nginx.pid;
  worker_processes     auto;
  worker_rlimit_nofile 65535;
  
  # Load modules
  include              /etc/nginx/modules-enabled/*.conf;
  
  events {
      multi_accept       on;
      worker_connections 65535;
  }
  
  http {
      charset                utf-8;
      sendfile               on;
      tcp_nopush             on;
      tcp_nodelay            on;
      server_tokens          off;
      log_not_found          off;
      types_hash_max_size    2048;
      types_hash_bucket_size 64;
      client_max_body_size   16M;
  
      # MIME
      include                mime.types;
      default_type           application/octet-stream;
  
      # Logging
      access_log             /var/log/nginx/access.log;
      error_log              /var/log/nginx/error.log warn;
  
      # Load configs
      include                /etc/nginx/conf.d/*.conf;
      include                /etc/nginx/sites-enabled/*;    #站点配置
  }
  ```

- 站点配置
	```nginx
	
	```

###### 3) 参考资料

  - [nginx documentation](http://nginx.org/en/docs/)
  - [Nginx开发从入门到精通](http://tengine.taobao.org/book/index.html)
  - [Nginx在线配置](https://www.digitalocean.com/community/tools/nginx?global.app.lang=zhCN)

##### 3.1.3 Openresty

###### 1) 参考资料

- [Openresty github]](https://github.com/openresty/openresty)

##### 3.1.4 Kong
###### 1) 参考资料
- [Kong OSS Docs](https://docs.konghq.com/gateway-oss/)
- [KongGuide code](https://github.com/KongGuide/Book)
- [KONG API Gateway v1.5](https://github.com/cloudframeworks-apigateway/user-guide-apigateway)
##### 3.1.5 Traefik
###### 1) 架构
![](microservice/gateway/traefik-architecture.png)
###### 2) 参考资料

- [Traefik Docs](https://doc.traefik.io/traefik/)
- [Traefik Book](https://www.qikqiak.com/traefik-book/getting-started/quick-start/)

#### 消息中间件
##### ☞ Kafka

> ![](https://gitee.com/yejinlei/about-bigdata/raw/master/%E6%9C%89%E5%85%B3Kafka.png)
> 摘自: https://gitee.com/yejinlei/about-bigdata

## 二. 容器及Kubernetes(原理及使用,详见:[yejinlei/about-os](https://gitee.com/yejinlei/about-os/))

​		容器是云原生应用的最小的构建单元，一次构建，到处运行;

​		Kubernetes是云原生操作系统，声明式 API 是它的核心，Operator 操控万物。

## 三. CI/CD & Devops

> **Continuous Integration (CI), 持续集成**
> ![](devops/ci.png)
> **Continuous Delivery (CD), 持续交付**
> ![](devops/cd.png)
> **Continuous Deployment, 持续部署**
> ![](devops/cdeployment.png)
> **DevOps, 开发自运维**
> ![](devops/devops_old.png)
> ![](devops/devops_new.png)

*参考资料*

- [The Product Managers’ Guide to Continuous Delivery and DevOps](https://www.mindtheproduct.com/what-the-hell-are-ci-cd-and-devops-a-cheatsheet-for-the-rest-of-us/)
- [刘相-加速企业敏捷的DevOps平台](devops/刘相-加速企业敏捷的DevOps平台.pdf)

## 四. 参考资料
1. [迁移到云原生应用架构](https://jimmysong.io/migrating-to-cloud-native-application-architectures/)