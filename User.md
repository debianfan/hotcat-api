##用户接口部分
---
###注册
|| *Status Code* || *Description* ||
|| 201 || 注册成功后返回201与 Location Header ||
|| 400 || 发生错误后返回400 ||
 
- 接口地址：/api/v1/account/register
- 接口形式：POST
- 输入参数：username, password
- 输出参数：code, message
- curl调用示例：curl -v -H "Accept: application/json" -H "Content-type: application/json" -X POST -d '{"username":"jerry", "password":"test"}' http://ihotcat.com/api/v1/account/register

