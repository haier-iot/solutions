
!> **更新时间**：{docsify-updated}  



### 方案介绍

![整体方案图片][sl6_ztfa]  

> 合作方路由器网关作为中控系统，集成海尔U+ 的设备端SDK（SmartDevice SDK）的设备控制功能，相当于APP接入海尔U+ IOT平台，实现设备入网功能、设备搜索功能、设备控制功能、接收状态变化上报功能、接收报警信息上报功能等。
  

> 实现效果：用户通过合作伙伴设备（比如：路由器）的APP，控制管理海尔设备。



### 方案设计


![方案设计][sl6_rjgc] 


如软件构成图，说明如下：
1、	所有的交互操作由合作方APP发起，经路由器中的双方协议转换，由SmartDevice SDK实际控制设备；
2、	红色部分是需要合作方实现的，包括合作方App、协议转换、账号管理服务、授权激活管理、以及集成SmartDevice SDK。



### 功能流程

**路由登录认证**

![路由登录认证][sl6_rz] 

【**说明**】：

（1）clientKey、clientSecret由合作方分配，用于合作方云验证请求的合法来源；

（2）AppId,AppKey 由U+云分配，用于U+云验证请求的合法来源；

（3）U+云到合作云认证主要目的是保证路由器是合作伙伴授权的（由合作方路由器到合作伙伴云认证），并且获取合作伙伴路由器代表的用户ID（openId），openId将用于后面绑定设备的用户标识，用于U+云标识一个用户。

【**登录认证作用**】：

（1） 设备添加时，确认用户的有效身份；

（2） SmartDevice SDK 与U+ 云 交互时的身份校验；

【**登录认证主要流程如下**】：

（1） 路由器启动认证流程；

（2） 合作方路由器到云认证（clientKey、gw_id、gw_code）,gw_id为路由器的唯一标识 ,gw_code为路由器的gw_id对应的key；

（3） 合作方云返回（appId、appKey、code）,code为 10分钟有效期的一次性授权码。

（4） 合作方路由器调用U+云的认证（appId、appKey、code） ,U+云调用合作方的认证接口（clientKey、clientSecret、code），合作方云对code进行认证，返回openId。

（5） U+云生成access_token，作为后续访问U+云 服务的认证token。

（6） U+云向 合作方路由器返回 access_token。


**SmartDevice SDK 流程简图**
![流程简图][sl6_sdklc] 


【**注意**】：

（1） 请按照如上流程进行初始化，直到添加设备完成；

（2）使用全功能库时，只需调用用户侧的设置日志接口， 不需要重复调用设备侧的设置日志接口；

（3）在任何回调函数内，禁止调用任何同步接口，以免阻塞线程导致SDK死锁；

（4）设备网卡就绪后，再执行smartdeviceSDK的初始化 ；

（5）对于初始化接口、添加设备接口、 设置 token 接口和订阅执行失败时，建议进行再次调用直至成功为止；

### 工作事项

![工作事项][sl6_gzsx] 




[^-^]:常用图片注释
[sl6_ztfa]:_media/_Solutions/sl6ztfa.png  

[sl6_rjgc]:_media/_Solutions/sl6rjgc.png
[sl6_rz]:_media/_Solutions/sl6rz.png
[sl6_gzsx]:_media/_Solutions/sl6gzsx.png
[sl6_sdklc]:_media/_Solutions/sl6_sdklc.png