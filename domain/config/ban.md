# 组合封禁策略使用说明文档

功能说明：针对客户遇到的攻击，提供console平台配置给客户配置组合封禁策略，包括（不限于）针对IP、referer、UA等响应头参数进行限制。

配置可提交多个策略，策略最多支持20条，可调整策略优先级，优先级自上而下；

每条策略支持单选或者多选匹配规则，规则包括IP、Referer、User-Agent、URL、method;

每条策略需客户提交的内容不一致，具体填写规则和示例如下:

逻辑补充：等于：黑名单，不等于：白名单

|匹配规则(多选)	|逻辑(单选）|	参数|	参数限制	|参数示例  |
|----|----|----|----|----|
|IP   	|等于/不等于	  	|客户填写，按回车符隔开  	|	500条  	|	1.1.1.1 <br />   1.2.3.0/24  	|
|User-Agent	  	|等于/不等于	  	|客户填写，按回车符隔开，模糊匹配	  	|100条  	|Chrome/122.0.0.0 Safari/537.36
|Referer  	|	等于/不等于  	|	客户填写，按回车符隔开  	|	100条  	|	*.aaa.ucloud.com  <br /> aaa.ucloud.com.cn	|
|URL  	|	等于/不等于	  	|客户填写，按回车符隔开  	|	100条  	|	http://.www.ttt1.com/1.txt <br /> ^https?:// [^/] +/dir1/dir2/(dir3_1|dir3_2).html$  	|
|method	  	|等于/不等于	  	|GET(默认)/POST  	| 二选一	  	|	GET  	|

配置示例
IP封禁：
![image](https://github.com/UCloudDoc-Team/ucdn/assets/89777962/e42a00ef-f0da-4b9c-a4c6-57b20060e540)


IP+UA+Referer封禁
![image](https://github.com/UCloudDoc-Team/ucdn/assets/89777962/b2172d33-8181-4980-978a-7b73c45629d6)

