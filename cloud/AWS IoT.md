# AWS IoT

## [AWS Greengrass](https://aws.amazon.com/cn/greengrass/)

## [AWS面对嵌入式设备的IoT服务－AWS Greengrass介绍](https://aws.amazon.com/cn/about-aws/events/webinar/embedded-device-iot-service-aws-greengrass06272017/)

## [AWS IoT 功能](https://aws.amazon.com/cn/iot-platform/how-it-works/#gateway)

Greengrass是一款边缘计算设备，用于模拟云上的编程接口，用于在设备无法连上云端IOT平台时，进行本地处理。

### AWS IoT 设备 SDK
AWS IoT 提供有 SDK，以帮助您轻松快速地连接硬件设备或移动应用程序。
- [MQTT](https://github.com/mcxiaoke/mqtt)、HTTP、WebSockets
- C、JavaScript、Arduino

### 设备网关
支持设备安全高效地与 AWS IoT 进行通信
- 发布/订阅模式交换消息
- MQTT、WebSockets 和 HTTP 1.1 协议
- 自动扩展，以支持 10 亿多台设备，而无需预配置基础设施

### 身份验证和授权
在所有连接点处提供相互身份验证和加密
- AWS 身份验证方法（称为“SigV4”）以及基于身份验证的 X.509 证书
- HTTP 的连接可以使用任一方法
- MQTT 的连接可以使用基于证书的身份验证
- WebSockets 的连接可以使用 SigV4。借助 AWS IoT
- 可以将所选的角色和/或策略映射到每个证书，以便授予设备或应用程序访问权限
- 您可以通过控制台或使用 API 创建、部署并管理设备的证书和策略
- 支持用户移动应用使用 Amazon Cognito 进行连接，Amazon Cognito 将负责执行必要的操作来为应用用户创建唯一标识符并获取临时的、权限受限的 AWS 凭证。

### 注册表
注册表将创建设备标识并跟踪元数据，如设备的属性和功能。

### 设备影子
- 可以创建每台设备的持久虚拟版（或“影子”），它包含设备的最新状态
- 保留每台设备的最后报告状态和期望的未来状态，即便设备处于离线状态
- 通过 API 或使用规则引擎，获取设备的最后报告状态或设置期望的未来状态。
- 设备影子提供始终可用的 REST API，使得构建与您的设备进行交互的应用程序更加轻松

### 规则引擎
- 可以构建 IoT 应用程序，收集、处理和分析互数据，根据数据执行操作
- 无需管理任何基础设施
- 规则引擎根据您定义的业务规则转换这些消息并将它们传输到另一台设备或云服务
- 可以应用至一台或多台设备中的数据，并且它可以并行执行一个或多个操作。
- 规则引擎还可以将消息路由到 AWS 终端节点，包括 AWS Lambda、Amazon Kinesis、Amazon S3、Amazon Machine Learning、Amazon DynamoDB、Amazon CloudWatch 和内置 Kibana 集成的 Amazon Elasticsearch Service
- 外部终端节点可以使用 AWS Lambda、Amazon Kinesis 和 Amazon Simple Notification Service (SNS) 进行连接。
- 使用类似 SQL 的语句编写规则。规则可以编写为采用不同的方式表示，具体取决于消息内容。
- 规则引擎将提供数十个可用于转换数据的可用功能，并且可以通过 AWS Lambda 创建无限个功能。

# 疑问

1. 证书验证身份是怎么一个过程？
2. 