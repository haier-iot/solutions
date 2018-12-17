
>**当前版本：** [微信绑定控制 V1.0](zh-cn/ChangeLog/sl2)   
**更新时间：** {docsify-updated} 

## 技术方案

### 整体流程  

![整体方案图片][sl1_ztfa]  




## 服务开通  

### 微信服务   


**微信服务简介**  

?> 海极网为智能硬件开发者提供的免费的微信连通服务，开发者可以快速实现微信控制智能设备的功能，仅需申请微信公众号，在海极网及微信公众号上填写设备及账号的信息就可轻松实现微信控制智能设备的功能，大大节省开发移动应用的时间及人力成本，节省开支。微信强大的用户基础也会帮助设备开发者为智能设备用户提供更好的用户体验。  

**开通条件**  

?> 申请开通微信服务的用户必须为企业用户，申请开通微信服务的硬件的状态可以为开发中、审核中、未通过、已上线。  

**开通流程**  

![软件构成图片][sl1_rjgc]  

#### 微信服务开通流程

> 开通微信服务，提供两个入口：  
1. [我的产品][MyProduct]——>我的硬件  
2. [开放中心][OpenCenter]——>服务——>微信服务

##### 海极网硬件开通微信服务  
**创建硬件**  

开发者中心——> [我的产品][MyProduct]——>我的硬件——>创建设备定义属性——>开发调试——>提交审核

**开通微信服务**  

审核通过后点击侧边栏【服务】下的添加服务——>开通微信服务  
注：保持开发者中心微信服务“接入信息页”页面打开状态，同时打开微信公众号开通设备功能。

![开通微信服务图片][WeChatServer]  

##### 微信公众号开通设备功能及添加产品  

**开通设备功能**   

进入微信公众平台，点击【添加功能插件】，申请开通设备功能。  
![添加功能插件图片][AddPlug-in]

**设备功能设置** 

点击【设备功能】，点击【设置】，点击【编辑】。修改服务器配置,填写 URL、Token。  

![设备功能][DeviceFunction]

Url 和 Token 填写的内容为海极网开发者中心——>微信服务“接入信息页”的服务地址信息。    
Url 在海极网对应的字段名称为“微信硬件回调地址”。Token 在海极网对应的字段名称为“Token（令牌）”。  
  
![海极网服务地址信息][token]

“消息加解密方式”按图勾选后点击【提交】。点击【启用】，弹出弹窗点击【确认】。  

![启用设置图片][EnableSettings]

**添加产品**  
 
点击：设备功能——>产品管理——>添加产品  

![添加产品图片][AddProduct]  

进入“基础资料登记”，内容参考下图勾选，详细操作请参考`http://iot.weixin.qq.com/wiki/new/index.html`。  
注：红框部分请按照图片勾选，其他信息根据您的产品实际填选。  

![资料登记图片][DataRegistration]   

点击【下一步】，进入产品能力登记  

![产品能力登记图片][AbilityRegister]

**在微信服务号中添加海极网服务器IP为白名单**  

点击微信公众号左侧导航栏：开发——>【基本配置】，点击IP白名单的【查看】，添加IP保存即可。  

![添加白名单图片][AddWhiteList]  

海极网对外IP白名单为：  
`203.130.41.24  、123.103.113.7、123.103.10.42、221.122.92.13、210.51.17.147、221.122.92.14、221.122.92.15、 221.122.92.16`  


##### 海极网填写微信公众号信息  

**我的产品——>我的硬件**  

若在“我的产品——>我的硬件”中开通微信服务，请在海极网开发者中心——>微信服务接入信息页面填写微信公众号信息并保存。  

![填写微信公众号图片][AddWeChatInfo]  


**开放中心——>服务**  

若在“开放中心——>服务”中开通微信服务，请在海极网开放中心——>微信服务接入信息页面填写微信公众号信息并保存。  

![填写微信公众号图片2][AddWeChatInfo2]  

> “微信公众号信息”来源于微信公众平台，详情如下 

公众号GID：点击设置——>公众号设置——>原始ID，如下图标注

![公众号GID图片][GID] 

公众号APPID和公众号APPSECRET：开发——>基本配置，如下图标注  

![公众号APPID图片][APPID] 

产品编号（公众号ProductId）：功能设备功能，如下图标注  

![公众号ProductId图片][ProductId] 

> 上传MP文件  

在微信服务号中进入开发:  
接口权限——>网页服务——>网页授权，点击【修改】点击网页授权域名的【设置】。下载MP文件，上传至海极网开发者中心微信服务接入信息页。  

![上传PM图片][UploadPM]   



##### 微信上填写授权回调页面域名  

在海极网填写公众号信息、文件上传,保存成功后，在微信服务号页面授权页面填写授权回调页面域名： 

![授权回调图片][CallBack]  

授权回调页面域名为开发者中心——>我的产品——>我的硬件——>微信服务接入信息页面，如下图标注  

![url图片][urlBaack]  



##### 微信公众平台配置菜单

在海极网上填写公众号信息，成功保存后生成菜单跳转地址。在微信服务号配置菜单时填写该跳转地址。  

![配置菜单图片][ConfigInfo]  

页面地址信息：  
开发者环境页面地址	`https://haigeek-kfz.haier.net/wechatservice/authorize?gid=XXX`  

**使用通用设备控制应用**  

在微信公众平台——>功能——>自定义菜单，定义菜单。
定义菜单时，使用海极网生成的菜单跳转地址（如下图所示），系统会默认跳转到通用设备
控制应用。  

![设备控制应用图片][deviceControlAPP]   

**使用自己开发的控制页面**    

如果希望使用自己开发的控制页面（H5），需要在海极网生成的菜单跳转地址后边加 redirect_uri 参数  则会跳转到参数指定的路径。系统会默认在跳转url后边追加相关业务参数。  
如果需要开发控制页面（H5）请联系U+FAE获取接口文档。  
`appId`：微信服务appid 如：`MB-DEVELOPERSITE-0000`  
`datestamp`：时间戳 如：`1495617201723`  
`webAppVersion`： 版本：`1.0.0`  
`sign=加密后的签名` 调用saas服务接口参数如：    
`41d2dd5c3a651100000000ab3f9000082dc40d439eec646de9b68c41cbe13a3b`
`accessToken`：海尔用户`token   TGT000000G0J000124IIFZA8EBPZB0`
`clientId`：客户端id  `wechatservice_1491400000069`

用户可根据以上业务参数用户可开发自己的saas服务  

##### 手机通过微信绑定设备  

在微信公众平台——>功能——>设备功能——>产品管理中，找到设备，并点击“产品详情“  

![产品二维码图片][AboutTwo-dimensional] 

点击“下载二维码“，实际生产中需要将二维码贴在产品上。  

![二维码图片][Two-dimensional] 

手机连接无线网  
用手机微信的“扫一扫“功能，扫描刚打开的二维码，长按设备的配网键，设备进入配网模式。  
点击“配置设备上网“，输入密码点击连接。

![设备上网图片][Device2Internet] 

注:开发中设备调试微信服务的网络环境要配置成开发者环境  

连接上设备后，会自动跳转，稍等片刻，会出现设备的列表，点击设备，并进行绑定。  
绑定完成后，进入公众号，此时显示“等待设备接入“，点击右下角的我的设备列表。  
跳转后进入设备列表，选择设备后，进行设备的控制。     

![设备列表图片][DeviceList]  

##### 设备上线后微信服务号设置  

设备在未上线阶段开通微信服务，设备上线后对微信服务号中的URL、授权回调页面域名、菜单跳转地址。即可在生产环境使用微信服务，控制设备。

**登陆微信服务号**  

1、修改URL为：`http://haigeek.haier.net/wechatservice/device_event`  
2、操作：设备功能——>设置——>停用——>确定——>修改——>修改url——>确定——>启用——>确定  

![操作生产环境图片][operation2sc]

3、修改菜单跳转地址为:`https://haigeek.haier.net/wechatservice/authorize?gid=XXXX`  
   操作：自定义菜单——>修改菜单跳转地址——>保存并发布

![修改菜单图片][ModifyMenu]

4、修改页面回调域名为：`haigeek.haier.net/wechatservice/authorize`  
   操作：开发-接口权限——>页面授权-修改——>网页授权域名-设置网页授权域名——>修改页面回调域名——>确定  

![修改域名图片][ModifyDomain]



### 设备管理  

设备管理udse服务联系优家技术支持人员。


### 设备数据订阅  

海极网——>云应用——>数据推送——>开通





[^-^]:常用图片注释
[sl1_ztfa]:_media/_Solutions/sl2ztfa.png  
[sl1_rjgc]:_media/_Solutions/sl2rjgc.png

[MyProduct]:http://developer.haigeek.com:7900/developercenter/static/index.html#/
[OpenCenter]:http://developer.haigeek.com:7900/developercenter/static/index.html#/apiStore/storeServices////
[WeChatServer]:_media/_Solutions/WeChatServer.png  
[AddPlug-in]:_media/_Solutions/AddPlug-in.png 
[DeviceFunction]:_media/_Solutions/DeviceFunction.png 
[token]:_media/_Solutions/token.jpg 
[EnableSettings]:_media/_Solutions/EnableSettings.jpg  
[AddProduct]:_media/_Solutions/AddProduct.png  
[DataRegistration]:_media/_Solutions/DataRegistration.png 
[AbilityRegister]:_media/_Solutions/AbilityRegister.png   
[AddWhiteList]:_media/_Solutions/AddWhiteList.png 
[AddWeChatInfo]:_media/_Solutions/AddWeChatInfo.png 
[AddWeChatInfo2]:_media/_Solutions/AddWeChatInfo2.png 
[GID]:_media/_Solutions/GID.png 
[APPID]:_media/_Solutions/APPID.png 
[ProductId]:_media/_Solutions/ProductId.png  
[UploadPM]:_media/_Solutions/UploadPM.png  
[CallBack]:_media/_Solutions/CallBack.png  
[urlBaack]:_media/_Solutions/urlBaack.jpg
[ConfigInfo]:_media/_Solutions/ConfigInfo.png
[deviceControlAPP]:_media/_Solutions/deviceControlAPP.png 
[AboutTwo-dimensional]:_media/_Solutions/AboutTwo-dimensional.png  
[Two-dimensional]:_media/_Solutions/Two-dimensional.png   
[Device2Internet]:_media/_Solutions/Device2Internet.png  
[DeviceList]:_media/_Solutions/DeviceList.png 
[operation2sc]:_media/_Solutions/operation2sc.png 
[ModifyMenu]:_media/_Solutions/ModifyMenu.png
[ModifyDomain]:_media/_Solutions/ModifyDomain.png