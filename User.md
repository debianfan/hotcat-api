##用户接口部分

### 1.注册

- 接口地址：/api/v1/account/register
- 接口形式：POST
- 输入参数：username, password(需要md5加密后传递)
- 输出参数：code, message, token
- curl调用示例：curl -v -H "Accept: application/json" -H "Content-type: application/json" -X POST -d '{"username":"jerry", "password":"cc03e747a6afbbcbf8be7668acfebee5"}' http://ihotcat.com/api/v1/account/register

*Status Code* | *Description*
:------------ | :------------
201 | 注册成功后返回201与 Location Header，并返回token，且用户是已登录状态
400 | 发生错误后返回400

-
### 2.登录
- 接口地址：/api/v1/account/login
- 接口形式：POST
- 输入参数：username, password(需要md5加密后传递)
- 输出参数：code, message, token
- curl调用示例：curl -v -H "Accept: application/json" -H "Content-type: application/json" -X POST -d '{"username":"jerry", "password":"098f6bcd4621d373cade4e832627b4f6"}' http://ihotcat.com/api/v1/account/login
- 备注：输入参数password需要在客户端做MD5加密操作，传递到服务器端的是MD5后的结果；返回的token作为后面其他需要验证用户身份时候使用，调用方式为直接在接口地址上?token=xxx形式传递这个token参数

*Status Code* | *Description*
:------------ | :------------
200 | 登录成功后返回200，并返回token
400 | 发生错误后返回400

-
### 3.退出
- 接口地址：/api/v1/account/logout
- 接口形式：GET
- 输入参数：无
- 输出参数：code, message
- curl调用示例：curl -v -H "Accept: application/json" -X POST -d '{}' http://ihotcat.com/api/v1/account/logout?token=2916f5b579f171214843c4ace26f3c15

*Status Code* | *Description*
:------------ | :------------
200 | 登录成功后返回200，并返回token
400 | 未登录状态返回400
-


### 4.获得当前用户信息
- 接口地址：/api/v1/account/login
- 接口形式：GET
- 输入参数：无
- 输出参数：code, message, username
- curl调用示例：curl -v -H "Accept: application/json" http://ihotcat.com/api/v1/account?token=2916f5b579f171214843c4ace26f3c15

*Status Code* | *Description*
:------------ | :------------
200 | 登录成功后返回200，并返回token
400 | 未登录状态返回400

-
### 5.修改密码
- 接口地址：/api/v1/account/changepassword
- 接口形式：POST
- 输入参数：oldPassword, newPassword
- 输出参数：code, message
- curl调用示例：curl -v -H "Accept: application/json" -H "Content-type: application/json" -X POST -d '{"oldPassword":"098f6bcd4621d373cade4e832627b4f6", "newPassword":"test123"}' http://ihotcat.com/api/v1/account/changepassword?token=2916f5b579f171214843c4ace26f3c15

*Status Code* | *Description*
:------------ | :------------
200 | 登录成功后返回200，并返回token
400 | 发生错误后返回400


