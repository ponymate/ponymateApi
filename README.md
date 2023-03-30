# Api开放平台

### 技术栈  

- Spring Boot 2.7.x（贼新）  
- Spring MVC  
- MyBatis + MyBatis Plus 数据访问（开启分页）  
- Spring Boot 调试工具和项目处理器  
- Spring AOP 切面编程  
- Spring Scheduler 定时任务  
- Spring 事务注解  
- Dubbo 远程调用  
- nacos 注册中心  
- Spring Cloud Gateway
- Spring Boot Start

### 数据存储  

- MySQL 数据库  
  
### 工具类  

- Hutool 工具库  
- Gson 解析库  
- Apache Commons Lang3 工具类  
- Apache Commons-collections4 集合工具类  
- Lombok 注解  
  
### 业务特性  

- 全局请求响应拦截器（记录日志）  
- 全局异常处理器  
- 自定义错误码  
- 封装通用响应类  
- Swagger + Knife4j 接口文档  
- 自定义权限注解 + 全局校验  
- 全局跨域处理  
- 长整数丢失精度解决  
- 多环境配置  

## 业务功能  

- 用户登录、注册、注销、更新、检索、权限管理  
- 接口创建、删除、编辑、上线、下线、接口测试  

## Api开放平台后台  

主要实现了对api接口的发布下线修改和测试  

## Api开放平台接口

被实际调用的接口。

主要为测试用，没有实际有用的接口。

## 客户端SDK

为每一个接口都实现了调用的方法，添加了带有ak和sk的请求头和带有数据的请求体并向目标接口发送了http请求。

## Api网关

在接口之前添加了网关，用来进行验证用户身份，记录接口被用户调用的次数等业务逻辑，
客户端sdk不直接发送请求到被调用的接口，而是发送到网关，由网关来统一进行业务逻辑并转发，还可以实现流量染色和访问控制等高级功能。

## Common包

定义了网关模块和后台模块均需要的调用一些通用的方法接口和实体类。便于使用dubbo进行远程调用


## 快速上手

### MySQL 数据库  

1）修改 `application.yml` 的数据库配置为你自己的：  

```yml  
spring:  
  datasource:  
    driver-class-name: com.mysql.cj.jdbc.Driver  
    url: jdbc:mysql://localhost:3306/ponymate_api  
    username: root  
    password: 123456  
```

2）执行 `sql/create_table.sql` 中的数据库语句，自动创建库表  

3）启动项目，访问 `http://localhost:8103/api/doc.html` 即可打开接口文档，不需要写前端就能在线调试接口了~
