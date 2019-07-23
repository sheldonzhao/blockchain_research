## 1. 什么是WeBASE

微众银行正式开源自研的区块链中间件平台——WeBASE (WeBank Blockchain Application Software Extension)是区块链应用和FISCO BCOS节点之间搭建的中间件平台，该平台适配支持FISCO BCOS底层平台，面向多种对象，如开发者、运营者，并根据不同的场景，包括开发、调试、部署、审计等，打造丰富的功能组件和实用工具，提供友好的、可视化的操作环境。

![image.png](https://upload-images.jianshu.io/upload_images/150344-eff7a29a2ea7eb84.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 2. 现阶段开发者痛点

1. 缺乏好用的智能合约开发工具，合约的开发和调试效率不高；难以便捷地管理链上各节点配置信息，观察其运行状态。

2. 区块链上的区块、交易、回执等数据的呈现方式不够友好，对链上的海量数据难以进行灵活和多维度的分析。

3. 针对参与到业务的各账号及其进行的交易行为，需要通用的审计工具，以便及时发现和杜绝异常。

### 基于WeBASE的应用开发流程

![image.png](https://upload-images.jianshu.io/upload_images/150344-8fa3fce447bd2fb1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 3. WeBASE 整体架构和设计原则

WeBASE的整体架构和设计原则：
![architecture](https://upload-images.jianshu.io/upload_images/150344-885cd54b8e536420.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![design](https://upload-images.jianshu.io/upload_images/150344-44bbfae13c45a651.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


WeBASE的设计理念是一个子系统解决一个问题，无需部署所有子系统就能跑起来，因此在设计之初就遵循如下原则：

按需部署：WeBASE对应用开发通用共性进行抽象，形成各类服务组件，如业务接入、私钥管理、交易队列、合约开发、数据导出、审计等，开发者根据需要部署所需组件。

微服务架构：WeBASE采用微服务架构，基于spring-boot框架，提供Restful风格接口。

零耦合：WeBASE所有子系统独立存在，均可独立部署，独立运行，面向不同的场景提供服务，避免出现“全家桶”式的冗余负担。

可定制：前端体验往往带有开发者自身的业务表现，如不同的样式、不同的交互风格、不同的品牌表现等，因此WeBASE采用前后端分离的设计，后端接口保持稳定和可扩展，前端页面则由开发者自由定制。

## 4. 基础模块

![modules](https://upload-images.jianshu.io/upload_images/150344-a776b4075a7223dc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![modules](https://upload-images.jianshu.io/upload_images/150344-4af665d72815f42a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* **智能合约IDE**: 在线编译、调试、测试、部署智能合约，高效的编辑环境，Solidity语法支持。
* **节点前置服务 [WeBASE-Front](https://github.com/WeBankFinTech/WeBASE-Front)** 
集成web3jsdk，提供restful风格的接口，客户端可以使用http的形式和节点进行交互，内置内存数据库，采集节点健康度数据。内置web控制台，实现节点的可视化操作。

* **节点管理服务 [WeBASE-Node-Manager](https://github.com/WeBankFinTech/WeBASE-Node-Manager)**
处理前端页面所有web请求，管理各个节点的状态，管理链上所有智能合约，对区块链的数据进行统计、分析，对异常交易的审计，私钥管理等。

* **WeBASE管理平台 [WeBASE-Web](https://github.com/WeBankFinTech/WeBASE-Web)**
可视化操作平台，可基于此平台查看节点信息，开发智能合约等。

* **交易服务 [WeBASE-Transcation](https://github.com/WeBankFinTech/WeBASE-Transcation)**
接收交易请求，缓存交易到数据库中，异步上链 (对无状态的交易进行缓存，实现异步上链，便于对链上链下进行数据一致性校验)，可大幅提升吞吐量，解决区块链的tps瓶颈。

* **私钥托管和签名服务 [WeBASE-Sign](https://github.com/WeBankFinTech/WeBASE-Sign)**
托管用户私钥，提供云端签名。
* **数据导出代码生成工具 [WeBASE-Codegen-Monkey](https://github.com/WeBankFinTech/WeBASE-Codegen-Monkey)**
代码生成工具，通过配置可以生成数据导出的核心代码。

* **数据导出服务 [WeBASE-Collect-Bee](https://github.com/WeBankFinTech/WeBASE-Collect-Bee)**
导出区块链上的基础数据，如当前块高、交易总量等，通过智能合约的配置，导出区块链上合约的业务数据，包括event、构造函数、合约地址、执行函数的信息等。

WeBASE代码仓库地址：
https://github.com/WeBankFinTech/WeBASE

联盟区块链底层技术平台: https://github.com/FISCO-BCOS/FISCO-BCOS 

社区文档：[https://webasedoc.readthedocs.io/zh_CN/latest/index.html](https://webasedoc.readthedocs.io/zh_CN/latest/index.html)

### 5. 界面功能展示

示例平台：154.8.215.133:3002 用户名admin密码Abcd12345

![数据概览](https://upload-images.jianshu.io/upload_images/150344-855c671cda538187.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![节点监控](https://upload-images.jianshu.io/upload_images/150344-4889039651652987.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![主机监控](https://upload-images.jianshu.io/upload_images/150344-b902d001536323b3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

