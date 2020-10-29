##项目目录划分  
### &ensp;&ensp;src : 项目源码目录  
```
  java  -- java源代码  
  	tao-application  
	tao-service  
	tao-client  
	tao-common  
	tao-model   
  web  -- 前台源代码  
	tao-merchant-manage -- 商家后台管理系统  
	tao-mall-h5        -- 商城h5手机  
	tao-platform-manage -- 平台后台管理系统 
```
### doc : 项目文档  
```
暂无
```
###config : 配置文件目录, 配置文件命名规范，项目名-工程类型-平台类型-模块名.properties, 对于平台类型，service工程为空，因为service是公用的
```
例如:
  tao-application-merchant-authentication.properties  -- tao商家平台基础模块配置信息
  tao-service-authentication.properties               -- tao基础服务
```
### sql : 项目脚本，SQL脚本名称必须按照模块进行
```
  self-test -- 自测脚本目录
      v1 -- 代表第几次提测，具体目录有多少，根据实际情况增加目录
         -- 各个模块命名文件，文件命令规范: 模块名-提测版本号-本模块顺序.sql,
		 -- 比如: merchant-v1-1.sql
      v2
      v3
      v4
  test  -- 测试脚本目录
        -- 各个模块的提测脚本最终需要放到一个目录里，例如merchant模块有多个自测文件,如下  
      merchant-v1-1.sql
      merchant-v2-1.sql
  product  -- 生产环境SQL，如果当前不是第一个版本，需要跑完上次product目录下的SQL，
  		 -- 并跑完test目录下的SQL，形成当前版本的SQL脚本
           -- 比如:
		   	当前版本是v4, 则需要跑v3版本该模块的SQL，以及v3版本test目录下该模块的增量SQL
      merchant.sql  -- 需要将每个模块的SQL，整理成一个文件。
```










