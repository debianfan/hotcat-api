##用户接口部分

### 1.注册

- 接口地址：/api/v1/account/register
- 接口形式：POST
- 输入参数：username, password
- 输出参数：code, message
- curl调用示例：curl -v -H "Accept: application/json" -H "Content-type: application/json" -X POST -d '{"username":"jerry", "password":"test"}' http://ihotcat.com/api/v1/account/register

*Status Code* | *Description*
:------------ | :------------
201 | 注册成功后返回201与 Location Header
400 | 发生错误后返回400

-

### 2.登录
- 接口地址：/api/v1/account/login
- 接口形式：POST
- 输入参数：username, password
- 输出参数：code, message, token
- curl调用示例：curl -v -H "Accept: application/json" -H "Content-type: application/json" -X POST -d '{"username":"jerry", "password":"098f6bcd4621d373cade4e832627b4f6"}' http://hotcat.dev/app_dev.php/api/v1/account/login

*Status Code* | *Description*
:------------ | :------------
200 | 登录成功后返回200，并返回token
400 | 发生错误后返回400

-

