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
> 简单来说，微服务架构风格是一种将一个单一应用程序开发为一组**小型**服务的方法，每个服务运行在自己的进程中，服务间通信采用轻量级通信机制(通常用HTTP资源API)。这些服务围绕业务能力构建并且可通过**全自动部署**机制**独立部署**。这些服务共用一个最小型的集中式的管理，服务可用不同的语言开发，使用不同的数据存储技术。                  - 摘自: YYGCui‘s Blog [微服务]([http://blog.cuicc.com/blog/2015/07/22/microservices/#%E8%BF%9B%E5%8C%96%E5%BC%8F%E8%AE%BE%E8%AE%A1](http://blog.cuicc.com/blog/2015/07/22/microservices/#进化式设计))


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
#### API网关服务

> ![](microservice/有关Nginx_OpenResty.png)

##### ☞ Nginx/OpenResty

​	*参考资料*

1. [Nginx开发从入门到精通](http://tengine.taobao.org/book/index.html)

##### ☞ Traefik

​	*参考资料*

​	1. [Traefik book](https://www.qikqiak.com/traefik-book/getting-started/quick-start/)

#### 消息中间件
##### ☞ Kafka

> ![](https://gitee.com/yejinlei/about-bigdata/raw/master/%E6%9C%89%E5%85%B3Kafka.png)
> 摘自: https://gitee.com/yejinlei/about-bigdata

## 二. 容器及Kubernetes(原理及使用,详见:[yejinlei/about-os](https://gitee.com/yejinlei/about-os/))

​		容器是云原生应用的最小的构建单元，一次构建，到处运行;

​		Kubernetes是云原生操作系统，声明式 API 是它的核心，Operator 操控万物。

## 三. CI/CD持续交付

## 四. DevOps开发与运维

## 五. 参考资料
1. [迁移到云原生应用架构](https://jimmysong.io/migrating-to-cloud-native-application-architectures/)