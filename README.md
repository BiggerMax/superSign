# IOS超级签名系统

应朋友要求做一个IOS超级签名系统，根据一篇文章 [蒲公英超级签名原理](https://www.jianshu.com/p/d535a3e09dd0) 开发了自己的一套超级签名系统，整个重签名的技术细节请参考这篇文章。

### 系统模块
	系统采用简易分布式架构，主要由三个模块构成：
|  项目   | 名称  |
|  ----  | ----  |
| api-consumer  | 实际IPA重签名子服务 |
| vue-admin-java  | 超级签名业务后端代码 |
| vue-admin-html-java  | 超级签名业务管理前端代码 |

### 部署结构
	* 针对C端和B端用户相关模块部署在阿里云，利用BGP网络的优势提高系统页面响应；
	* 将大带宽要求的api-consumer部署到自己机房，以减少重签名时IPA包的传输时间；
	* 用阿里云OSS作分发，开启传输加速，网络资源较好；
	* 在阿里云上安装redis做消息队列，与重签名子服务保持调度； 

### 重签名服务器

针对这块研究了好久，第一个方案是找Mac云主机，只找到国外有这种Mac云主机，价格还不便宜，最终测试下来还是因为网络太差而放弃了这个方案；第二个方案转到在linux上安装isign来代替Mac机器，但实际是isign也是各种报错而跑不起来；第三个方案采用Mac mini托管到机房，作为重签名服务器算是跑起来了。

### 截图
安装界面
![avatar](img/img1.png)

管理后台
![avatar](img/img2.png)

### 技术交流
此项止仅供学习交流
作者QQ: 55720091
