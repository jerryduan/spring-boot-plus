# Spring Boot Plus 项目介绍

## 项目概述

Spring Boot Plus 是一个基于 Spring Boot 2.7.18 的开源快速开发脚手架，集成了常用的开发组件和最佳实践，旨在帮助开发者快速构建高质量的企业级应用。项目采用前后端分离的单体架构，提供了完整的后台管理系统和移动端 API 接口，使开发者能够独立、高效地进行项目开发。






## 核心特性

- **完整的权限管理系统**：包含用户、角色、菜单、权限等完整的权限控制体系
- **代码生成器**：一键生成前后端代码，包括 entity/dto/query/vo/controller/service/mapper/xml
- **多端支持**：同时支持管理后台和移动端 API 接口
- **接口文档**：集成 Swagger/Knife4j，自动生成 API 文档
- **缓存支持**：集成 Redis 缓存，提高系统性能
- **数据库操作**：集成 MyBatis Plus，简化 DAO 层操作
- **日志系统**：完善的日志记录和管理功能
- **文件上传**：支持本地和 OSS 文件上传
- **前端项目**：配套 Vue3+TypeScript 的前端项目





## 技术栈

### 后端技术

| 技术 | 版本 | 说明 |
|------|------|------|
| Spring Boot | 2.7.18 | 应用开发框架 |
| MyBatis | 3.5.13 | ORM 框架 |
| MyBatis Plus | 3.5.4.1 | MyBatis 增强工具 |
| Fastjson2 | 2.0.42 | JSON 处理工具 |
| Swagger | V3 | API 文档生成 |
| Knife4j | 4.3.0 | API 文档增强 |
| Hutool | 5.8.23 | 工具类库 |
| Lombok | 1.18.30 | 注解处理器 |
| Redis | 3.2+ | 缓存数据库 |

### 前端技术

- Vue 3.2
- TypeScript
- Element Plus
- Vite
- Pinia
- Vue Router







## 项目结构

```
spring-boot-plus
├── docs                    # 文档和配置文件
├── db                      # 数据库脚本
└── src
    ├── main
    │   ├── java
    │   │   └── io
    │   │       └── geekidea
    │   │           └── boot
    │   │               ├── auth            # 认证授权模块
    │   │               ├── common          # 公共模块
    │   │               ├── config          # 配置类
    │   │               ├── framework       # 核心框架
    │   │               ├── generator       # 代码生成器
    │   │               ├── system          # 系统管理
    │   │               ├── user            # 用户模块
    │   │               ├── util            # 工具类
    │   │               └── SpringBootPlusApplication.java  # 启动类
    │   └── resources
    │       ├── mapper                      # MyBatis XML 映射文件
    │       ├── static                      # 静态资源
    │       ├── templates                   # 代码生成模板
    │       ├── application.yml             # 主配置文件
    │       ├── application-dev.yml         # 开发环境配置
    │       ├── application-test.yml        # 测试环境配置
    │       └── application-prod.yml        # 生产环境配置
    └── test                                # 测试代码
```






## 核心模块说明

### 1. 认证授权模块 (auth)

负责系统的登录认证、权限验证、令牌管理等功能，支持管理后台和移动端两种认证方式。主要特点：

- 基于 Token 的身份验证
- 角色权限控制
- 数据范围权限
- 登录信息缓存

### 2. 系统管理模块 (system)

提供系统核心功能，包括：

- 用户管理：系统用户的增删改查
- 角色管理：角色的分配与权限设置
- 菜单管理：系统菜单配置
- 字典管理：系统字典数据维护
- 系统配置：全局参数配置
- 系统日志：操作日志记录与查询

### 3. 代码生成器 (generator)

强大的代码生成功能，支持：

- 数据库表结构可视化
- 自定义代码模板
- 一键生成前后端代码
- 支持多种生成策略

### 4. 框架核心 (framework)

系统的核心组件，包括：

- 全局异常处理
- 统一响应封装
- AOP 日志记录
- 数据权限控制
- MyBatis 增强功能
- Redis 缓存支持

### 5. 用户模块 (user)

面向 C 端用户的功能模块，包括：

- 用户注册登录
- 用户信息管理
- 用户角色分配






## 快速开始

1. **环境准备**：
   - JDK 1.8+
   - MySQL 5.7+
   - Redis 3.2+

2. **数据库初始化**：
   - 创建数据库 `spring_boot_plus`
   - 执行 `db/mysql_spring_boot_plus.sql` 脚本

3. **配置修改**：
   - 修改 `application-dev.yml` 中的数据库连接信息
   - 修改 Redis 配置

4. **启动项目**：
   - 运行 `SpringBootPlusApplication.java` 主类
   - 访问 `http://localhost:8888/api/doc.html` 查看接口文档
   - 默认管理员账号：admin，密码：123456

5. **代码生成**：
   - 修改 `src/test/java/io/geekidea/boot/generator/Generator.java` 配置
   - 运行生成器生成代码






## 代码生成流程

1. 创建数据库表，遵循命名规范
2. 配置代码生成器参数（包名、模块名、作者等）
3. 指定要生成的表名和表前缀
4. 运行代码生成器
5. 生成的代码包括：实体类、DTO、查询对象、服务层、控制器、Mapper 等






## 项目特色

1. **开箱即用**：集成常用组件，无需繁琐配置
2. **代码规范**：遵循最佳实践，代码风格统一
3. **性能优化**：集成高性能连接池和缓存
4. **安全性**：完善的权限控制和参数校验
5. **易扩展**：模块化设计，便于功能扩展
6. **文档完善**：自动生成 API 文档，降低沟通成本






## 开源协议

本项目使用 MIT 开源协议，任何个人或公司都可以免费使用，无需授权。

## 相关链接

- 前端项目：[spring-boot-plus-vue3](https://gitee.com/geekidea/spring-boot-plus-vue3)
- GitHub 仓库：[https://github.com/geekidea/spring-boot-plus](https://github.com/geekidea/spring-boot-plus)
- Gitee 仓库：[https://gitee.com/geekidea/spring-boot-plus](https://gitee.com/geekidea/spring-boot-plus)
