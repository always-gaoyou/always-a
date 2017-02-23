# 1. Which Java microservice frameworks
- Spring

>   [Microservices with Spring](https://spring.io/blog/2015/07/14/microservices-with-spring)


- MSF4J

> [WSO2 Microservices Framework for Java (MSF4J) ](https://github.com/wso2/msf4j)


# 2. Comparsion

> [A comparison of Microservices Frameworks](https://cdelmas.github.io/2015/11/01/A-comparison-of-Microservices-Frameworks.html)

> [Top 8 Java RESTful Micro Frameworks](http://www.gajotres.net/best-available-java-restful-micro-frameworks/)

# 3. Opinion

> [1. Microservice need infrastructer](http://www.infoq.com/cn/articles/basis-frameworkto-implement-micro-service)

![image](http://cdn2.infoqstatic.com/statics_s1_20170221-0307u1/resource/articles/basis-frameworkto-implement-micro-service/zh/resources/1125004.png)

- LB Layer
> - Load Balance

>>LVS, HAProxy

> - Soft LB
>>using Service Registry, eg.Zookeeper, Consul, Etcd...

>- Standalone LB
>> airbnb's SmartStack,
> Zookeeper作为服务注册表，Nerve独立进程负责服务注册和健康检查，Synapse/HAproxy独立进程负责服务发现和负载均衡

- Gateway Layer

> ```
> 1. 服务反向路由，网关要负责将外部请求反向路由到内部具体的微服务，这样虽然企业内部是复杂的分布式微服务结构，但是外部系统从网关上看到的就像是一个统一的完整服务，网关屏蔽了后台服务的复杂性，同时也屏蔽了后台服务的升级和变化。
> 2. 安全认证和防爬虫，所有外部请求必须经过网关，网关可以集中对访问进行安全控制，比如用户认证和授权，同时还可以分析访问模式实现防爬虫功能，网关是连接企业内外系统的安全之门。
> 3. 限流和容错，在流量高峰期，网关可以限制流量，保护后台系统不被大流量冲垮，在内部系统出现故障时，网关可以集中做容错，保持外部良好的用户体验。
> 4. 监控，网关可以集中监控访问量，调用延迟，错误计数和访问模式，为后端的性能优化或者扩容提供数据支持。
> 日志，网关可以收集所有的访问日志，进入后台系统做进一步分析。
> 
> 除以上基本能力外，网关还可以实现线上引流，线上压测，线上调试(Surgical debugging)，金丝雀测试(Canary Testing)，数据中心双活(Active-Active HA)等高级功能。
> ```
> 
> - Netflix's Zuul

- Service Layer

> - 服务容错

>> Circuit Breaker Patten

>> Bulkhead Isolation Pattern

>> Rate Limiting/Load Shedder

>> fallback

> - 服务框架

>>![image](http://cdn2.infoqstatic.com/statics_s1_20170221-0307u1/resource/articles/basis-frameworkto-implement-micro-service/zh/resources/1125008.png)

>> Swagger是一种流行Restful API的文档方案。

>> Netflix的Karyon/Ribbon

>> Spring的Spring Boot/Cloud，

>> Alibaba的Dubbo

- Runtime config
> 配置中心比较成熟的开源方案有百度的Disconf，360的QConf，Spring的Cloud Config和阿里的Diamond等

- Netflix frameworks


```
Eureka:　服务注册发现框架
Zuul:　服务网关
Karyon:　服务端框架
Ribbon:　客户端框架
Hystrix: 服务容错组件
Archaius: 服务配置组件
Servo: Metrics组件
Blitz4j: 日志组件
```


> [2. All framework and tools](https://yq.aliyun.com/articles/68675)

> Introduce the Netflix OSS package.

> [3. Huawei cloudy microservive archintecture](http://www.infoq.com/cn/presentations/evolution-of-huawei-cloud-micro-service-architecture?utm_campaign=rightbar_v2&utm_source=infoq&utm_medium=presentations_link&utm_content=link_text)

> -  如何推行于化架构?
> 1. 对照12因子

> 2. 采用微服务架构

>```
>– 建立服务设计的方法论
>– 建立配套平台解决架构复杂度
>```

> 3. 基础公共服务能力
>```
>– 架构能力的体现
>```

> 4. 持续交付
>```
>– 端到端的支撑工具 
>– 可视化、智能化
>```

> 5. 敏捷基础设施
>```
>– 通过云抽象资源，屏蔽物理设施。提供弹性、按需的资源能力。
>```
> 6. 组织层面-康威定律

