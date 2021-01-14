# Soul极简入门

------

## 本节概述

- 搭建网关环境
- 运行 soul-admin 和 soul-bootstrap

## 主要内容

### 通读文档

建议大家和我一样，不管能看懂多少，先尝试通读一下 Soul 的[官方文档](https://dromara.org/zh-cn/docs/soul/soul.html)后，再进行下面的操作。

### 拉取代码

首先，先把 Soul 的代码拉下来，安装 Google 浏览器插件或者通过 gitee clone 速度会快一点。先 fork 到自己的 github，命令如下：

```
git clone https://github.com/dromara/soul
```

### 熟悉 Soul 的项目结构

soul-admin：插件和其他配置信息的管理后台
soul-bootstrap：网关核心
soul-client：
soul-common：框架通用类
soul-dashboard：soul-admin的前端项目
soul-dist：
soul-examples：示例项目
soul-metrics：
soul-plugin：
soul-register-center：
soul-api：
soul-spring-boot-starter：
soul-sync-data-center：
soul-web：
逐步学习，逐步完善。。。

### 编译并运行项目

```
mvn clean package install -Dmaven.test.skip=true -Dmaven.javadoc.skip=true -Drat.skip=true -Dcheckstyle.skip=true
```

#### 运行 soul-admin

编译成功后，启动自己本地的 MySQL，并根据自己的数据库配置，修改 soul-admin 项目下 resources/application-local.yml 文件，配置正确的可访问的 mysql 地址。

运行 soul-admin 项目的 SoulAdminBootstrap.java ，系统会自动生成数据库 soul 和 所使用的表，如下图：

<img src="picture/Soul%E6%9E%81%E7%AE%80%E5%85%A5%E9%97%A8/image-20210115003039958.png" alt="image-20210115003039958" style="zoom:50%;" />

通过配置文件或者控制台日志均可获取 soul-admin 启动在 9095 端口，访问 [http://localhost:9095](http://localhost:9095/) 并使用 admin 123456 就可以成功登录 soul 的管理后台了。

![image-20210115004412748](picture/Soul%E6%9E%81%E7%AE%80%E5%85%A5%E9%97%A8/image-20210115004412748.png)

登录成功后的界面：可以在右上角进行国际化语言切换（中/英）。

![image-20210115004559655](picture/Soul%E6%9E%81%E7%AE%80%E5%85%A5%E9%97%A8/image-20210115004559655.png)

soul-admin 的数据流程图：

<img src="picture/Soul%E6%9E%81%E7%AE%80%E5%85%A5%E9%97%A8/plugin-data.png" alt="img" style="zoom:50%;" />

#### 运行 soul-bootstrap

编译成功后，修改 soul-bootstrap 项目配置文件 application-local.yml 中 websocket 的 urls 配置，改为上一步运行 soul-admin 项目的访问地址。

运行 SoulBootstrapApplication.java 启动项目。

#### 运行 soul-examples-http

编译成功后，修改 soul-examples-http 项目配置文件 application.yml 中 http 的 adminUrl 配置，改为运行 soul-admin 项目的访问地址。

运行 SoulTestHttpApplication.java 启动项目。

启动成功后，可以在 soul-admin 管理后台中插件列表查看 divide 插件状态以及规则列表，如下图：

![image-20210115023311766](picture/Soul%E6%9E%81%E7%AE%80%E5%85%A5%E9%97%A8/image-20210115023311766.png)

访问 soul-examples-http 项目的请求，http://localhost:8188/order/findById?id=3 ，响应结果符合预期。

![image-20210115023452513](picture/Soul%E6%9E%81%E7%AE%80%E5%85%A5%E9%97%A8/image-20210115023452513.png)

通过 soul-bootstrap 网关访问 soul-examples-http 项目，soul-bootstrap 项目的端口为9195，soul-examples-http 项目 配置的soul.http.contextPath 为 /http ，所以访问 http://localhost:9195/http/order/findById?id=3 ，响应结果符合预期。

![image-20210115024552579](picture/Soul%E6%9E%81%E7%AE%80%E5%85%A5%E9%97%A8/image-20210115024552579.png)

## 知识拓展

### 相关文章推荐

### 知识点拓展

