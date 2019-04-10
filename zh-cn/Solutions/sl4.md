
>**当前版本：** [海尔账号Oauth授权 V1.0](zh-cn/ChangeLog/sl4)   
**更新时间：** {docsify-updated} 



### 方案介绍



![整体方案图片][sl4_ztfa]  

?>  合作方应用通过海尔账号OAUTH授权登录的方式，获取海尔账号的用户资源信息，包括用户的智能设备内容以及实现智能设备的操作等。  


### 方案设计


![整体方案图片][sl4zx]  

**1、账号认证**  

?> 合作方应用通过海尔账号OAUTH方式得到海尔用户的授权。

**2、设备信息**  

?> 合作方应用得到海尔用户的授权后，获取用户在U+ 平台的智能设备信息。


**3、设备操作**  

?> 合作方应用通过调用U+ IOT平台的UWS API rest 接口服务实现智能的设备控制等物联场景。  


### 方案应用


?> 方案应用于AI语音设备商等具备一定研发能力，使用海尔账号的OAUTH服务实现用户授权，完成对用户设备的控制的合作方。







<!-- 
## 功能流程 &emsp;
-->







[^-^]:常用图片注释
[sl4_ztfa]:_media/_Solutions/sl4ztfa.png  
[sl4zx]:_media/_Solutions/sl4zx.png  


[sl4_rjgc]:_media/_Solutions/sl4rjgc.png