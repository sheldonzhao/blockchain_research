## 1. 什么是WeIdentity

WeIdentity是一套微众银行自主研发并完全开源的实体身份标识与可信数据解决方案，可承载实体对象（人或者物）的现实身份与链上身份的可信映射、以及实现实体对象之间安全的访问授权与数据交换。”

WeIdentity目前主要包含两大模块：WeIdentity DID以及WeIdentity Credential。

1．分布式身份标识 (WeIdentity DID)

WeIdentity DID模块在FISCO-BCOS区块链底层平台上实现了一套符合W3C DID规范的分布式多中心的身份标识协议，使实体（人或物）的现实身份实现了链上的身份标识；同时，WeIdentity DID给与Subject（人或者物）直接拥有和控制自己身份ID的能力。

2．可验证数字凭证 (WeIdentity Credential)

现实世界中存在着各种各样用于描述实体身份、实体间关系的数据，如身份证、行驶证、存款证明、处方、毕业证、房产证、信用报告等。WeIdentity Credential提供了一整套基于W3C VC规范的解决方案，旨在对这一类数据进行标准化、电子化，生成可验证、可交换的凭证（Credential）。

在官方GitHub上，列出了5类应用场景的案例，分别是：新入职员工背景调查、医疗检查结果与处方可信流转、选择性披露、政务办理、慈善公益。

以政务办理为例，居民政务数据存在于不同部门，跨部门的政务办理往往需要先至部门A开具证明，再至部门B进行办理。对居民而言，流程繁琐且文件不易管理与保存；对政府部门而言，希望提升用户体验并确保用户隐私数据不泄露。通过WeIdentity解决方案，可以为居民生成可信的电子证件，居民授权后由机构进行验证，从而简化业务流程，降低隐私数据泄露风险。

WeIdentity官网：[https://fintech.webank.com/weidentity](https://fintech.webank.com/weidentity)

WeIdentity源代码：[https://github.com/WeBankFinTech/WeIdentity](https://github.com/WeBankFinTech/WeIdentity)

区块链备案信息：
![](https://upload-images.jianshu.io/upload_images/150344-9982ffd423d8478a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

除WeIdentity之外，这次备案的企业中还有 4 个项目也是身份信息上链及应用的相关项目。

![image.png](https://upload-images.jianshu.io/upload_images/150344-17de2a1ab2944ae0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## 2. 机遇与挑战

### 2.1 机遇

1.市场需求巨大

根据市场研究机构Smithers Pira预测，2016–2021年，身份和接入管理市场的规模将从80.9亿美元增长至148.2亿美元，年复合增长率达到12.9%。其中，亚洲将占全球个人身份市场的60%以上，按人民币折算，2021年亚洲市场为600亿元。

2.政策鼓励支持

工业和信息化部发布的《大数据产业发展规划（2016－2020年）》明确提出：要树立数据开放共享理念，完善相关制度，推动数据资源开放共享与信息流通，促进跨行业、跨领域、跨地域大数据应用，形成良性互动的产业发展格局。

3.行业方兴未艾

近两年来，政府支持或企业、产业联盟主导的大数据交易平台多地开花，但尚处初级和探索阶段，未形成行业规范和规模效应。而基于实体认证和可信数据交换的数据管理平台更处于萌芽阶段，少有应用案例。

### 2.2 挑战

1.数据孤岛

第一，数据场景化、碎片化，造成数据源是多而零散的；第二，数据管理呈现寡头化的趋势，数据寡头占有大量数据，但又并不能完全覆盖所有用户信息；第三，数据类型复杂、标准不一，数据交换缺乏信任源、安全难保障等诸多原因造成数据交换难、共享难。

2.数据滥用

个人作为数据主体的角色缺失，用户授权机制不完善，隐私保护的法律法规、事后追责机制等相关体系仍需不断发展完善，这些原因都造成了数据滥用问题的普遍存在。

3.数据黑产

《中国网络空间安全发展蓝皮书》显示，每年我国因个人信息泄露等遭受的经济损失高达数千亿。网络黑产已从半公开化的纯攻击模式转化为敛财工具和商业竞争手段，已形成跨平台、跨行业的犯罪链条。

## 3. WeIdentity产品方案

各个参与者共同来完成整个身份验证的流程。首先，由实体对象（即拥有链上身份 ID 的人或物）向若干机构申请身份凭证；接着，用户代理（一般是权威可信机构如某政府部门）为用户生成链上 ID 并提供 KYC 服务。完成认证后，实体可选择将自己的各项数据授权给若干机构使用；此时，使用数据的机构可选择购买一些凭证验证方的服务，后者可协助多方该实体的数据是否被篡改、是否经过凭证发行方认证（指对数据进行发行和认证的机构或个体）。在实体将其身份和数据上传后，还有一个专门的数据托管机构来确保实体的数据被安全存储。

![](https://upload-images.jianshu.io/upload_images/150344-f798e8c5182fdb60.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![image.png](https://upload-images.jianshu.io/upload_images/150344-5c6808ead81d10af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 4. WeIdentity应用场景

### 4.1 WeIdentity旗舰应用：澳门智慧城市建设之“证书电子化”项目

解决方案：基于联盟链的解决方案：WeIdentity

项目参与方：
* 澳门身份证明局（负责澳门居民的身份认证）
* 澳门生产力中心、澳门理工大学等证书发行方（负责提供职业培训课程、专业考试及管理的政府机构，以及提供学历及学位证书的高校）
* 澳门电讯等企业（澳门电讯等企业）

流程：
1. 用户在移动端授权用户代理处理证书相关服务
2. 用户代理为澳门居民创建链上唯一的WeID
3. 身份证明局为澳门居民进行身份验证
4. 证书发行方使用WeID生成证书Credential并将证明摘要上传到区块链
5. 验证方将链下获取的原证书内容，与WeID Credential进行校验

![image.png](https://upload-images.jianshu.io/upload_images/150344-65c25f2681e5cf3b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

方案优势：
1. 证书电子化管理
2. 跨机构信息交互
3. 信息真实性验证

### 4.2 其他应用场景概述

![image.png](https://upload-images.jianshu.io/upload_images/150344-eb51616be5352b71.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 场景一：新入职员工背景调查

1. 员工、学校、公司分别进行WeIdentity DID注册及KYC认证。
2. 员工向学校学校申请学历证明凭证（Credential）、学位证明凭证（Credential）。
3. 员工向前雇主公司申请工作证明凭证（Credential）、离职证明凭证（Credential）。
4. 员工将这些凭证（Credential）挂到自己的个人主页上，或者直接提交给现雇主公司。
5. 现雇主公司通过凭证验证（Verify）接口对上述凭证（Credential）进行验证。
6. 验证通过，现雇主公司发放入职offer。

#### 场景二：医疗检查结果与处方可信流转

1. 患者、医院、药店分别进行WeIdentity DID注册及KYC认证。
2. 患者就诊过程中，医院对患者生成各项医疗检查凭证（Credential），并开具处方凭证（Credential）。
3. 患者将这些凭证保存在本地数据库里（如手机等移动存储媒介）。
4. 患者在其他医院进行复诊时，可直接出示以上凭证（Credential），不需出示纸质检查结果及处方。
5. 其他医院可通过凭证验证（Verify）接口进行验证，并在此基础上提供医疗服务。
6. 患者在药店开药时，亦可出示以上凭证（Credential）并由药店通过凭证验证（Verify）接口进行验证。
7. 验证通过，药店开药。
8. 保险机构亦可通过凭证验证（Verify）接口进行验证，验证通过，为患者进行保险理赔。

#### 场景三：选择性披露

1. 实体人及娱乐机构进行WeIdentity DID注册及KYC认证。
2. 实体人向娱乐机构进行选择性披露，只披露KYC认证（Credential）的DID、有效期、出生日期等信息，隐藏其他信息。
3. 娱乐机构通过凭证验证（Verify）接口对选择性披露的数据进行验证。
4. 验证通过，允许进入。

#### 场景四：数据共享

1. 在身份证明机构、数据持有机构、数据使用机构间搭建区块链网络，机构作为节点接入并注册WeIdentity DID
2. 由身份证明机构为用户进行KYC并生成WeIdentity DID
3. 用户授权数据使用机构使用自己的数据
4. 数据使用机构生成授权凭证（Credential），标明授权对象、数据属主、有效期、授权内容等属性，并使用机构私钥进行签名；数据使用机构可选择将授权凭证生成摘要并写入区块链，达到增信目的
5. 数据使用机构出示授权凭证给数据持有机构
6. 数据持有机构通过凭证验证（Verify）接口，验证授权凭证
7. 验证通过，数据持有机构将数据发送给数据使用机构


## 5. WeIdentity技术方案

#### 设计目标
------------

.. raw:: html

<embed>
<table border='1' style="width:100%;border-collapse:collapse">
<tr>
<th width="100">目标</th>
<th>说明</th>
</tr>
<tr>
<td>多中心</td>
<td>分布式多中心的ID注册机制，摆脱对传统模式下单一中心ID注册的依赖</td>
</tr>
<tr>
<td>开源开放</td>
<td>技术方案完全开源，面向政府、企业、开发者服务</td>
</tr>
<tr>
<td>隐私保护</td>
<td>实体的现实身份和可验证数字凭证的内容进行链下存储。支持实体将信息最小化或者选择性披露给其他机构，同时防止任何第三方反向推测出实体在现实世界或其他场景语义中的身份</td>
</tr>
<tr>
<td>可移植性</td>
<td>基于WeIdentity规范，数据可移植至遵循同样规范的其他平台，兼容业务主流区块链底层平台</td>
</tr>
<tr>
<td>互操作性</td>
<td>提供标准化接口，支持跨链、跨平台互操作</td>
</tr>
<tr>
<td>可扩展性</td>
<td>保证操作性，可移植性或简单性的情况下，数据模型可以通过多种不同方式进行扩展</td>
</tr>
</table>
<br />
</embed>

#### 什么是DID，Credential，Document 

WeIdentity DID用来描述实体（人或物），WeIdentity Credential用来描述实体的身份、属性和实体间关系。因此，一个WeIdentity DID可以持有多个WeIdentity Credential；而一个WeIdentity Credential则会包含至少一个所描述的WeIdentity DID，可能会有多个。最后，每个WeIdentity DID都有一个WeIdentity Document，用来存储此DID的认证方式（如公钥、私钥套件）等信息，与WeIdentity Credential无关。

![image.png](https://upload-images.jianshu.io/upload_images/150344-f44b76a0754d7df5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 如何生成WeIdentity DID
**WeIdentity DID = did:weid:net-id:bs-specific-string**

![](https://upload-images.jianshu.io/upload_images/150344-5656ef7caabb633d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Credential结构
^^^^^^^^^^^^^^

.. list-table::
:header-rows: 1

* - 属性
- 说明
* - @context
- 用于描述Credential的字段信息等
* - id
- 本Credential的ID，按UUID生成
* - issuer
- Issuer的DID，遵从WeIdentity规范
* - issued
- issue日期
* - claim
- Claim的具体细节，数据结构由CPT定义，详见CPT介绍
* - claim.primeNumberIdx
- 素数在素数表中的index
* - claim.type
- Claim Protocol Type的ID，申请按序递增，例如中国内地驾照设置为CPT100
* - revocation
- 撤销相关实现，待补充
* - signature
- Issuer的签名列表，是一个数组，可由holder和issuer分别打上签名
* - signature.type
- 签名类型
* - signature.created
- 签名的创建时间
* - signature.creator
- 签名机构的WeIdentity DID
* - signature.domain
- domain
* - signature.nonce
- 随机数
* - signature.signatureValue
- 签名的具体value，对整个Credential结构中除去signature字段的其他字段做签名

WeIdentity Document格式
^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
:header-rows: 1

* - 字段
- 说明
* - @context
- 用于描述WeIdentity Document结构等信息
* - id
- WeIdentity DID，表示当前Document描述的Entity，用于自描述
* - created
- Document的创建时间
* - updated
- Document的更新时间
* - publicKey
- 公钥数组列表，格式如下
* - publicKey.id
- 公钥的ID
* - publicKey.type
- 用于指定signature suite
* - publicKey.owner
- 指定控制对应私钥的Entity，遵从WeIdentity规范，如果为空，则表明owner是Document的id字段，如果是Credential类Entity，则owner一般是某用户
* - authentication
- 用于Entity证明其与当前Document的关联性
* - authentication.type
- 用于指定signature suite
* - authentication.publicKey
- 用来验证签名的公钥，引用publicKey数组里定义的公钥
* - service
- service描述数组，用于描述跟当前DID相关的服务，格式如下
* - service.id
- service endpoint的ID
* - service.type
- service endpoint的协议
* - service.serviceEndpoint
- serviceEndpoint列表，可以是URI或者一个JSON-LD对象
* - service.其他
- 待定
* - recovery
- WeIdentity DID私钥丢失后，可由本字段指定的WeIdentity进行公私钥重置。是否需要抽象一层合约层来实现待定



## 6. 参考文档

应用场景文档：[https://weidentity.readthedocs.io/zh_CN/latest/docs/use-cases.html](https://weidentity.readthedocs.io/zh_CN/latest/docs/use-cases.html)

WeIdentity 规范文档：[https://weidentity.readthedocs.io/zh_CN/latest/docs/weidentity-spec.html](https://weidentity.readthedocs.io/zh_CN/latest/docs/weidentity-spec.html)

