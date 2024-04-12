## /caipiao/获取最新开奖号码
```text
暂无描述
```
#### 接口状态
> 开发中

#### 接口URL
> https://cp.usdt123.site/api/latest

#### 请求方式
> POST

#### Content-Type
> json

#### 请求Body参数
```javascript
{
	"appid": "120240412140311",
	"now": "2024-04-12 15:00:51",
	"sign": "3c25ccbbd017b38aae79d1bdec741885"
}
```
参数名 | 示例值 | 参数类型 | 是否必填 | 参数描述
--- | --- | --- | --- | ---
appid | 120240412140311 | String | 是 | 应用id
now | 2024-04-12 15:00:51 | String | 是 | 当前时间，必须是北京时间
sign | 3c25ccbbd017b38aae79d1bdec741885 | String | 是 | 签名
#### 成功响应示例
```javascript
{
	"status": 1,
	"msg": "操作成功",
	"data": {
		"expect": 13103882,
		"code": "0,0,1,9,3",
		"time": "2024-04-12 14:51:45",
		"nexttime": "2024-04-12 14:53:00",
		"nextexpect": 13103883,
		"type": 100,
		"name": "极速时时彩",
		"createtime": "2024-04-12 14:51:57"
	}
}
```
参数名 | 示例值 | 参数类型 | 参数描述
--- | --- | --- | ---
status | 1 | Integer | 状态，大于0代表成功，小于0代表失败
msg | 操作成功 | String | 描述
data | - | Object | 数组
data.expect | 13103882 | Integer | 当期期号
data.code | 0,0,1,9,3 | String | 开奖号码
data.time | 2024-04-12 14:51:45 | String | 开奖时间
data.nexttime | 2024-04-12 14:53:00 | String | 下一期开奖时间
data.nextexpect | 13103883 | Integer | 下一期期号
data.type | 100 | Integer | 彩票类型
data.name | 极速时时彩 | String | 彩票名字
data.createtime | 2024-04-12 14:51:57 | String | 创建时间，北京时间
#### 签名算法
```php
//php代码示例
function sign($data, $appkey){
    ksort($data);
    $str = '';
    foreach($data as $key=>$value){
        if($key == 'sign'){
            continue;
        }
        $str = $str . $key . '=' . $value . '&';
    }
    $str = substr($str,
    0,
    -1);
    if($appkey != ''){
        $str = $str . $appkey;
    }
    $sign = md5($str);
    return $sign;
}
```
## /caipiao/测试签名
```text
暂无描述
```
#### 接口状态
> 开发中

#### 接口URL
> https://cp.usdt123.site/api/sign

#### 请求方式
> POST

#### Content-Type
> json

#### 请求Body参数
```javascript
{
	"appid": "120240412140311",
	"now": "2024-04-12 15:00:51",
	"sign": "3c25ccbbd017b38aae79d1bdec741885"
}
```
参数名 | 示例值 | 参数类型 | 是否必填 | 参数描述
--- | --- | --- | --- | ---
appid | 120240412140311 | String | 是 | 应用id
now | 2024-04-12 15:00:51 | String | 是 | 当前时间，必须是北京时间
#### 成功响应示例
```javascript
{
	"status": 1,
	"msg": "success, 签名正确，签名是: 3c25ccbbd017b38aae79d1bdec741885",
	"data": []
}
```
参数名 | 示例值 | 参数类型 | 参数描述
--- | --- | --- | ---
status | 1 | Integer | 状态，大于0代表成功，小于0代表失败
msg | success, 签名正确，签名是: 3c25ccbbd017b38aae79d1bdec741885 | String | 描述
data | - | Array | 数组
#### 签名算法
```php
//php代码示例
function sign($data, $appkey){
    ksort($data);
    $str = '';
    foreach($data as $key=>$value){
        if($key == 'sign'){
            continue;
        }
        $str = $str . $key . '=' . $value . '&';
    }
    $str = substr($str,
    0,
    -1);
    if($appkey != ''){
        $str = $str . $appkey;
    }
    $sign = md5($str);
    return $sign;
}
```