
>**当前版本：** [ToB用户开发APP设备功能指南 V1.0](zh-cn/ChangeLog/sl7)   
**更新时间：** {docsify-updated} 



### 介绍  

?> 本方案为B平台（企业级）APP开发者开发设备功能详情界面提供指导。
  

### 前提    

?> 硬件开发者需在海极网创建设备或已有采购的海尔设备。可参考《U+开放平台产品接入操作手册》。 


### 名词解释  

**设备功能模板：**    

某一大类设备的功能集文档，由海极网提供，通常该大类一般对应一个设备功能模板。例如柜机空调设备对应柜机空调模板、分体空调设备对应分体空调模板、等等。  


**设备功能模型文档：**  

从某品类的设备功能模板中选取需要的功能集，这些功能集就是设备功能模型文档，由海极网提供。


**TypeId：**   

设备类型标识的唯一识别码，由64字节的 16 进制数值组成。同一个TypeId设备下包含了多个不同型号的设备。硬件开发者在海极网创建设备后生成TypeId。  

**设备型号：**   

设备规格的一种标志。购买后见设备使用说明书。  

#### 关系图  

![关系图][sl7_er] 


### 开发APP设备功能流程  

  

![业务流程图片][sl7_yewu]   

例如，某B端平台选定了一批设备（比如XX1型号的冰箱）与U+平台进行对接，需要根据冰箱类设备功能模板和自身业务现状，选取冰箱类设备的公共功能进行设备功能界面模板开发，然后根据XX1型号的功能模型文档与已开发好的设备功能界面模板进行匹配渲染，从而显示或隐藏相应的功能界面；交付运营一段时间后，该平台需要增加XX2型号的冰箱，进行功能升级，此时B端平台只需要根据新型号的功能模型文档，与事先开发的冰箱类功能界面模板进行匹配渲染即可，无需重新进行对接开发工作，如果冰箱类设备功能模板界面里没有XX2型号的功能则需开发者自行添加。  


### U+ APP参考     
 
![整体方案图片][sl7_ztfa]    



### 设备功能模板获取方式  

  
?> 联系海极网王少辉（wangshaohui@haier.com）获取。  



### 设备功能模型文档获取方式  

?> 联系海极网王少辉（wangshaohui@haier.com）获取。  





[^-^]:常用图片注释
[sl7_ztfa]:_media/_Solutions/sl7jiemian.png  

[sl7_rjgc]:_media/_Solutions/sl7rjgc.png  

[sl7_er]:_media/_Solutions/sl7er.png    

[sl7_yewu]:_media/_Solutions/sl7liucheng.png    

[sl7_login]:_media/_Solutions/sl7login.png  

[sl7_register]:_media/_Solutions/sl7register.png   

[sl7_creat]:_media/_Solutions/sl7creat.png     

[sl7_app]:_media/_Solutions/sl7app.png    

[sl7_info]:_media/_Solutions/sl7info.png 

[sl7_sdk]:_media/_Solutions/sl7usdk.png  

[sl7_world]:_media/_Solutions/sl7world.png 

[sl7_resources]:_media/_Solutions/sl7resources.png   

[sl7_server]:_media/_Solutions/sl7server.png   
