
!> **更新时间**：{docsify-updated}  




### 方案介绍

![整体方案图片][sl5_ztfa]  

?> 合作方云与U+ IOT云平台的对接采用云云账号对接方式，互相访问交互认证的机制，保证访问安全流畅，实现海尔智能设备的配网、绑定和设备控制。  

?> 实现效果：用户通过合作伙伴的APP，实现发现海尔设备，配网、绑定和控制海尔设备。


### 方案设计


![整体方案图片][sl5_rjgc] 


如软件构成图，说明如下：
1、	所有的交互操作由自第三方APP发起，设备配置绑定操作通过合作方App集成海尔U+ uSDK来实现，通过调用U+的设备控制服务实现设备控制；<br/>
2、	合作方云端需要开发回调接口用于U+ IOT回调鉴权，实现云云互联；<br/>
3、	红色部分是需要合作方实现的，包括合作方App、协议转换、登录认证、以及App集成U+ uSDK。


### 功能流程

**登录认证**

![整体方案图片][sl5rz]  

【**说明**】：

（1）clientKey、clientSecret由合作方分配，用于合作方云验证请求的合法来源；

（2）AppId,AppKey 由U+云分配，用于U+云验证请求的合法来源；

（3）U+云到合作云认证主要目的是保证合作伙伴授权的合法性，并且获取合作方代表的用户ID（openId），openId将用于后面绑定设备的用户标识，用于U+云标识一个用户。

【**登录认证作用**】：

（1） 设备添加时，确认用户的有效身份；

（2） app的U+ uSDK 与U+ 云 交互，以及访问U+ 平台设备管理服务时的身份校验；




### 工作事项

![工作事项][sl5_gzsx] 





[^-^]:常用图片注释
[sl5_ztfa]:_media/_Solutions/sl5ztfa.png  
[sl5rz]:_media/_Solutions/sl5rz.png  
[sl5bd]:_media/_Solutions/sl5bd.png  
[sl5kz]:_media/_Solutions/sl5kz.png 

[sl5_rjgc]:_media/_Solutions/sl5rjgc.png
[sl5_gzsx]:_media/_Solutions/sl5gzsx.png