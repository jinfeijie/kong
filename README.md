[![][kong-logo]][kong-url]

[![Build Status][badge-travis-image]][badge-travis-url]
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/Kong/kong/blob/master/LICENSE)
[![Twitter](https://img.shields.io/twitter/follow/thekonginc.svg?style=social&label=Follow)](https://twitter.com/intent/follow?screen_name=thekonginc)

Kong是一个云原生，快速，可扩展，支持分布式的微服务抽象层 *（有时候也可以称为API网关，API中间件，甚至在某些情况下可以称为服务网格）* 。2015年以开源的形式发布，它最重要的点在于它的高性能和可扩展性。

> Kong is a cloud-native, fast, scalable, and distributed Microservice Abstraction Layer *(also known as an API Gateway, API Middleware or in some cases Service Mesh)*. Made available as an open-source project in 2015, its core values are high performance and extensibility.


在积极维护的情况下，Kong被广泛应用于各类初创企业，全球5000强企业甚至政府机构的生产环境上。
> Actively maintained, Kong is widely used in production at companies ranging
from startups to Global 5000 as well as government organizations.

[安装（Installation）](https://konghq.com/install) |
[文档（Documentation）](https://docs.konghq.com) |
[论坛（Forum）](https://discuss.konghq.com) |
[博客（Blog）](https://konghq.com/blog) |
IRC (freenode): [#kong](https://webchat.freenode.net/?channels=kong) |
[Nightly Builds][kong-nightly-master]

## 总结（Summary）

- [**为什么要使用Kong（Why Kong）?**](#why-kong)
- [**特性（Features）**](#features)
- [**分配（Distributions）**](#distributions)
- [**开发（development）**](#development)
- [**企业支持和演示（Enterprise Support & Demo）**](#enterprise-support--demo)
- [**许可证（License）**](#license)

## Why Kong?

如果你正在为web应用、移动应用或物联网应用构建通用功能的软件。Kong可以充当微服务请求的网关（或Sidecar），同时可以通过插件提供负载均衡、日志记录、身份验证、速率限制、转换等功能。
> If you are building for the web, mobile, or IoT (Internet of Things) you will likely end up needing common functionality to run your actual software. Kong can help by acting as a gateway (or a sidecar) for microservices requests while providing load balancing, logging, authentication, rate-limiting, transformations, and more through plugins.

[![][kong-benefits]][kong-url]

## Features

- **云原生**: 不论什么平台，Kong在裸机到Kubernetes上都可以运行
- **Cloud-Native**: Platform agnostic, Kong can run from bare metal to
  Kubernetes.

- **动态负载均衡**: 跨多个上游服务的流量负载均衡。
- **Dynamic Load Balancing**: Load balance traffic across multiple upstream
  services.

- **基于哈希的负载均衡**: 具有一致的哈希/粘性会话的负载平衡。
- **Hash-based Load Balancing**: Load balance with consistent hashing/sticky
  sessions.

- **熔断器**: 智能跟踪不健康的上游服务。
- **Circuit-Breaker**: Intelligent tracking of unhealthy upstream services.

- **健康检查:** 主动和被动监控你的上游服务。
- **Health Checks:** Active and passive monitoring of your upstream services.

- **服务发现**: 在Consul等第三方DNS解析器中解析SRV记录。
- **Service Discovery**: Resolve SRV records in third-party DNS resolvers like
  Consul.

- **无服务器**：在Kong上可以直接调用并保护AWS Lambda或OpenWhisk函数。
- **Serverless**: Invoke and secure AWS Lambda or OpenWhisk functions directly
  from Kong.

- **WebSockets**: 通过WebSockets与您的上游服务进行通信。
- **WebSockets**: Communicate to your upstream services via WebSockets.

- **OAuth2.0**: 轻松地将OAuth2.0身份验证添加到API上。
- **OAuth2.0**: Easily add OAuth2.0 authentication to your APIs.

- **日志**: 通过HTTP、TCP、UDP或磁盘记录系统的请求和响应。
- **Logging**: Log requests and responses to your system over HTTP, TCP, UDP,
  or to disk.

- **安全**: ACL，机器人检测，白名单/黑名单IP等...
- **Security**: ACL, Bot detection, whitelist/blacklist IPs, etc...

- **日志**: 记录到系统日志。
- **Syslog**: Logging to System log.

- **SSL**: 为底层服务或API设置特定SSL证书。
- **SSL**: Setup a Specific SSL Certificate for an underlying service or API.

- **监控**: 实时监控提供关键的负载和性能服务指标。
- **Monitoring**: Live monitoring provides key load and performance server
  metrics.

- **转发代理**: 使Kong连接到中间透明的HTTP代理。
- **Forward Proxy**: Make Kong connect to intermediary transparent HTTP proxies.

- **认证**: HMAC, JWT, Basic等.
- **Authentications**: HMAC, JWT, Basic, and more.

- **限流**: 根据许多变量阻止和限制请求。
- **Rate-limiting**: Block and throttle requests based on many variables.

- **转换**: 添加，删除或操作HTTP请求和响应。
- **Transformations**: Add, remove, or manipulate HTTP requests and responses.

- **缓存**: 在代理层缓存并提供响应。
- **Caching**: Cache and serve responses at the proxy layer.

- **CLI**: 从命令行控制您的Kong群集。
- **CLI**: Control your Kong cluster from the command line.

- **REST API**: Kong可以使用RESTful API进行操作，以获得最大的灵活性。
- **REST API**: Kong can be operated with its RESTful API for maximum
  flexibility.

- **地理副本**: 配置始终是跨区域保持最新
- **Geo-Replicated**: Configs are always up-to-date across different regions.

- **故障检测和恢复**: 如果你的一个Cassandra节点发生故障，Kong不会受到影响。
- **Failure Detection & Recovery**: Kong is unaffected if one of your Cassandra
  nodes goes down.

- **集群**: 所有Kong节点自动加入群集，使其配置在节点之间更新。
- **Clustering**: All Kong nodes auto-join the cluster keeping their config
  updated across nodes.

- **可扩展性**: 按性质分布，Kong通过简单地添加节点进行横向扩展。
- **Scalability**: Distributed by nature, Kong scales horizontally by simply
  adding nodes.

- **性能**: Kong的核心使用Nginx，通过伸缩轻松处理负载
- **Performance**: Kong handles load with ease by scaling and using NGINX at
  the core.

- **插件**: 通过可扩展的架构，向Kong和API添加功能。
- **Plugins**: Extendable architecture for adding functionality to Kong and
  APIs.

有关插件和集成的更多信息，您可以查看[Kong Hub](https://docs.konghq.com/hub/)
> For more info about plugins and integrations, you can check out the [Kong
Hub](https://docs.konghq.com/hub/).

## Distributions

Kong 有很多种形式。虽然此存储库包含其核心的源代码，但其他存储库也在积极开发中：
> Kong comes in many shapes. While this repository contains its core's source code, other repos are also under active development:

- [Kong Docker](https://github.com/Kong/docker-kong): 一个用于运行Kong的Dockerfile。
- [Kong Packages](https://github.com/Kong/kong/releases): Debian、Red Hat和OS X发行版的预构建包（随每个版本一起提供）。
- [Kong Vagrant](https://github.com/Kong/kong-vagrant): 为Kong提供一个准开发环境的vagrantfile。
- [Kong Homebrew](https://github.com/Kong/homebrew-kong): Homebrew Formula for Kong.
- [Kong CloudFormation](https://github.com/Kong/kong-dist-cloudformation): 在AWS EC2上一键部署Kong
- [Kong AWS AMI](https://aws.amazon.com/marketplace/pp/B06WP4TNKL): Kong AMI on the AWS Marketplace.
- [Kong on Microsoft Azure](https://github.com/Kong/kong-dist-azure): 使用Azure资源管理器运行Kong。
- [Kong on Heroku](https://github.com/heroku/heroku-kong):在Heroku上一键部署Kong。
- [Kong and Instaclustr](https://www.instaclustr.com/solutions/managed-cassandra-for-kong/): 让Instaclustr管理您的Cassandra集群。
- [Kubernetes Ingress Controller for Kong](https://github.com/Kong/kubernetes-ingress-controller):
  Use Kong for Kubernetes Ingress.
- [Nightly Builds][kong-nightly-master]:在太平洋标准时间9AM构建可用的主分支。

## Development

如果你打算在开发Kong，你需要安装开发版本。分支`next`上有最新未发布的源代码。
> If you are planning on developing on Kong, you'll need a development installation. The `next` branch holds the latest unreleased source code.


你可以在[插件开发向导](https://docs.konghq.com/latest/plugin-development/)中阅读更多关于编写一款自己的插件的内容，或者在[插件开发工具包（PDK）参考](https://docs.konghq.com/latest/pdk/)中浏览Kong源代码文档的在线版本.
> You can read more about writing your own plugins in the [Plugin Development
Guide](https://docs.konghq.com/latest/plugin-development/), or browse an online version of Kong's source code documentation in the [Plugin Development Kit (PDK) Reference](https://docs.konghq.com/latest/pdk/).

#### Docker

按照[Kong/kong-build-tools](https://github.com/Kong/kong-build-tools#developing-kong)上的说明,你可以使用docker/docker-compose和挂载系统卷来开发Kong。
> You can use Docker / docker-compose and a mounted volume to develop Kong by following the instructions on [Kong/kong-build-tools](https://github.com/Kong/kong-build-tools#developing-kong).


#### Vagrant

你可以在[Kong/kong-vagrant](https://github.com/Kong/kong-vagrant)上找到相关资料，使用一个Vagrant box来运行Kong和Postgres。
> You can use a Vagrant box running Kong and Postgres that you can find at
[Kong/kong-vagrant](https://github.com/Kong/kong-vagrant).

#### 源码安装（Source Install ）

Kong主要是一个由Lua源文件构成的OpenResty应用程序，但也需要一些额外的第三方依赖项。我们建议你按照https://docs.konghq.com/install/source/上的源安装说明来安装它们。
> Kong mostly is an OpenResty application made of Lua source files, but also requires some additional third-party dependencies. We recommend installing those by following the source install instructions at https://docs.konghq.com/install/source/.


⚠️不要直接进入到第二步安装Kong

复制这个代码仓库，来安装最新的Lua源代码（否则会安装成当前发布的Lua源代码，就不利于开发了）
> Instead of following the second step (Install Kong), clone this repository and install the latest Lua sources instead of the currently released ones:

```shell
$ git clone https://github.com/Kong/kong
$ cd kong/

# you might want to switch to the development branch. See CONTRIBUTING.md
$ git checkout next

# install the Lua sources
$ luarocks make
```

#### 运行开发版本（Running for development）

查看默认配置文件的[development section](https://github.com/Kong/kong/blob/next/kong.conf.default#L244)，以便对属性进行调整，来简化Kong的开发过程。
> Check out the [development section](https://github.com/Kong/kong/blob/next/kong.conf.default#L244) of the default configuration file for properties to tweak in order to ease the development process for Kong.

修改[`lua_package_path`](https://github.com/openresty/lua-nginx-module#lua_package_path)和[`lua_package_cpath`](https://github.com/openresty/lua-nginx-module#lua_package_cpath)命令将允许Kong在系统中找到定制插件的源代码。
> Modifying the [`lua_package_path`](https://github.com/openresty/lua-nginx-module#lua_package_path) and [`lua_package_cpath`](https://github.com/openresty/lua-nginx-module#lua_package_cpath) directives will allow Kong to find your custom plugin's source code wherever it might be in your system.

#### 测试（Tests）

安装开发依赖项（[Busted]、[LuaCheck]）时使用：
> Install the development dependencies ([busted], [luacheck]) with:

```shell
$ make dev
```

Kong依靠使用[busted]测试库的三个测试套件：
> Kong relies on three test suites using the [busted] testing library:

* 单元测试
* Unit tests

* 集成测试，需要Postgres和Cassandra启动并运行
* Integration tests, which require Postgres and Cassandra to be up and running

* 插件测试，要求Postgres运行
* Plugins tests, which require Postgres to be running


The first can simply be run after installing busted and running:

```
$ make test
```

不管怎样，集成测试和插件测试将生成一个Kong实例并对其执行测试。
因此，根据您的需求，参考/编辑“spec/kong_tests.conf”，使您的测试实例指向您的Postgres/Cassandra服务器。
> However, the integration and plugins tests will spawn a Kong instance and perform their tests against it. As so, consult/edit the `spec/kong_tests.conf` configuration file to make your test instance point to your Postgres/Cassandra servers, depending on your needs.

您可以运行集成测试（假设Postgres和Cassandra都根据配置`spec/kong_tests.conf`运行）：
> You can run the integration tests (assuming **both** Postgres and Cassandra are running and configured according to `spec/kong_tests.conf`) with:

```
$ make test-integration
```

插件测试：
> And the plugins tests with:

```
$ make test-plugins
```

最后，只需使用以下命令即可立即运行所有套件：
> Finally, all suites can be run at once by simply using:

```
$ make test-all
```

请参阅[run_tests.sh](.ci/run_tests.sh)脚本，以获取测试套件和Makefile的更高级示例用法。
> Consult the [run_tests.sh](.ci/run_tests.sh) script for a more advanced example usage of the tests suites and the Makefile.

最后，Lua开发中的一个非常有用的工具（与许多其他动态语言一样）是执行代码的静态linting。 您可以使用[luacheck]\(与`make dev` 一起安装\)：
> Finally, a very useful tool in Lua development (as with many other dynamic languages) is performing static linting of your code. You can use [luacheck]\(installed with `make dev`\) for this:

```
$ make lint
```

#### Makefile

开发时，可以使用`Makefile`执行以下操作：
> When developing, you can use the `Makefile` for doing the following operations:

| Name               | Description                                            |
| ------------------:| -------------------------------------------------------|
| `install`          | 完全安装Kong luarock                                   |
| `dev`              | 安装开发依赖项                                         |
| `lint`             | Lint Lua 文件 in `kong/` and `spec/`                   |
| `test`             | 运行单元测试套件                                       |
| `test-integration` | 运行集成测试套件                                       |
| `test-plugins`     | 运行插件测试套件                                       |
| `test-all`         | 一次运行所有单元+集成+插件测试                         |

## Enterprise Support & Demo

如果你在一个大型组织工作，你应该了解更多关于[Kong企业版](https://konghq.com/kong-enterprise-edition/).
> If you are working in a large organization you should learn more about [Kong Enterprise](https://konghq.com/kong-enterprise-edition/).

## License

```
Copyright 2016-2019 Kong Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

[kong-url]: https://konghq.com/
[kong-logo]: https://konghq.com/wp-content/uploads/2018/05/kong-logo-github-readme.png
[kong-benefits]: https://konghq.com/wp-content/uploads/2018/05/kong-benefits-github-readme.png
[kong-nightly-master]: https://bintray.com/kong/kong-nightly/master
[badge-travis-url]: https://travis-ci.org/Kong/kong/branches
[badge-travis-image]: https://travis-ci.org/Kong/kong.svg?branch=master

[busted]: https://github.com/Olivine-Labs/busted
[luacheck]: https://github.com/mpeterv/luacheck
