## nike snkrs 分析

原文地址：https://github.com/zhaojunlike/nike-snkrs-api

snkrs bot api


> 1.akamai ai 风控系统 100% 过，3端数据mock api 任选
> 2.cookies 检测100%过 提供生成api



该项目只提供演示api调用结果，目前实现功能：

-   [x] 登录
-   [x] 注册
-   [x] 抢货
-   [x] AI 真人模拟
-   [x] cookies生成
-   [x] akamai AI风控过检
-   [x] 自动养号，代理IP


![2019-10-06-11-27-15](https://blog-oeynet-com.oss-cn-chengdu.aliyuncs.com/e4f179895c1713b25d26d273c6c6379e.png)


登录流程：

```

1.访问登录页面

set-cookie: bm_sz=B37D70D8485724389F741A447D64272E~YAAQBWgDF6U8cJptAQAAW/fEngVzLQr34OcGkuRpuk4fkQXEwRg5Lm5HNVt/eX6LN3+MqPSQ8xRfoEtv8nKjfH+BIoPT1zlo5jKXftf04XKsq1I+ZxKjIpmcx7Eg8rxrVPOjmsMt9t73rkY722b2+xtnuf/Gp1ABBh6n+b4jDgKIbBQhEx/b5sPSUryZsVtToQ==; Domain=.nikecdn.com; Path=/; Expires=Sun, 06 Oct 2019 05:52:51 GMT; Max-Age=14400; HttpOnly
set-cookie: _abck=7FA9F8070CB4ECCF0D932306A0EE19EC~-1~YAAQBWgDF6Y8cJptAQAAW/fEngLnhueJqG/zWlL5St0uvc7Jq4H1rTTH+m5g7BInjI/x7P6G6wS1NU5+XlKM+mjRpQspjqGPcnc2p3btMBL5IjdLvoABWU5QeH2AWQW4zd0ko9s4d342xm5nebmCAt9Hg43UJsDHHFB5msUW+NlsM+0+qGsGxS3NDlagvxboOnOPG3TER3lj+4/gPO5IxVoS5zP5K3hJm8pFLhUOKA7oLD6D+6U4AcXwmlpdWy1Gm6vvU/Epz9S9lKWP5t/ZHEom/Pp4/NK4XWho9/ug4P0lCpAV2Vk50ZsIHw==~-1~-1~-1; Domain=.nikecdn.com; Path=/; Expires=Mon, 05 Oct 2020 01:52:51 GMT; Max-Age=31536000; Secure


2.注册cookie到sensor_data
GET
cookie: bm_sz=B37D70D8485724389F741A447D64272E~YAAQBWgDF6U8cJptAQAAW/fEngVzLQr34OcGkuRpuk4fkQXEwRg5Lm5HNVt/eX6LN3+MqPSQ8xRfoEtv8nKjfH+BIoPT1zlo5jKXftf04XKsq1I+ZxKjIpmcx7Eg8rxrVPOjmsMt9t73rkY722b2+xtnuf/Gp1ABBh6n+b4jDgKIbBQhEx/b5sPSUryZsVtToQ==
cookie: _abck=7FA9F8070CB4ECCF0D932306A0EE19EC~-1~YAAQBWgDF6Y8cJptAQAAW/fEngLnhueJqG/zWlL5St0uvc7Jq4H1rTTH+m5g7BInjI/x7P6G6wS1NU5+XlKM+mjRpQspjqGPcnc2p3btMBL5IjdLvoABWU5QeH2AWQW4zd0ko9s4d342xm5nebmCAt9Hg43UJsDHHFB5msUW+NlsM+0+qGsGxS3NDlagvxboOnOPG3TER3lj+4/gPO5IxVoS5zP5K3hJm8pFLhUOKA7oLD6D+6U4AcXwmlpdWy1Gm6vvU/Epz9S9lKWP5t/ZHEom/Pp4/NK4XWho9/ug4P0lCpAV2Vk50ZsIHw==~-1~-1~-1
x-requested-with: com.nike.snkrs


3.上传用户数据
post


4.进行登录

cookie: bm_sz=B37D70D8485724389F741A447D64272E~YAAQBWgDF6U8cJptAQAAW/fEngVzLQr34OcGkuRpuk4fkQXEwRg5Lm5HNVt/eX6LN3+MqPSQ8xRfoEtv8nKjfH+BIoPT1zlo5jKXftf04XKsq1I+ZxKjIpmcx7Eg8rxrVPOjmsMt9t73rkY722b2+xtnuf/Gp1ABBh6n+b4jDgKIbBQhEx/b5sPSUryZsVtToQ==
cookie: _abck=7FA9F8070CB4ECCF0D932306A0EE19EC~-1~YAAQBWgDF8A+cJptAQAAwTXFngKDLhcRfNXmKGRrcQj7GMBLX8ceaRQv3rrGvdx8bRxveQWFZIH/7UHoyZiITOYI3fRwGXXeoXxfEvLmuJb8KWC5Mba+ZLtzlDtdOXdkSOlwGxZK6GnnZW2Vw/YlfXhMovfyUdGnhtjDYDQWM9OpZvBupfHkpYkDbkj8wSd9+1TNjSRe/oKNLGCyrIVG6NE2EjfXtjVhdxwsV0R8sEm8k1+Tz3l7BSbTtETFM4h0ZQz7aLzKJjx2m5sBV3Zw2zYzhKNi7qRIuwY4xHcPFBAfYfkB1AKX2hXRRM7xjsxEmLT7Vh5VU6Nh/SFLGfVmYtPy/37J~-1~-1~-1
x-requested-with: com.nike.snkrs

//可能,如果登录失败，要么切换设备ID，要么上传错误信息后拿到cookie重新登录
https://unite.nike.com/error?platform=android&browser=uniteSDK&mobile=true&native=true&uxid=com.nike.commerce.snkrs.droid&locale=zh_CN&osVersion=24&sdkVersion=2.8.1&backendEnvironment=identity&url=https%3A%2F%2Fs3.nikecdn.com%2Flogin%3FappVersion%3D638%26experienceVersion%3D638%26uxid%3Dcom.nike.commerce.snkrs.droid%26locale%3Dzh_CN%26backendEnvironment%3Didentity%26browser%3DGoogle%2520Inc.%26os%3Dundefined%26mobile%3Dtrue%26native%3Dtrue%26visit%3D1%26visitor%3Dc36c3bfa-6700-43cd-bc7b-72a23c398b34&errorMsg=HTTP+error+message%3A++and+code%3A+401
```


## 协议开放API列表

![2019-10-11-13-50-10](https://blog-oeynet-com.oss-cn-chengdu.aliyuncs.com/6e12afb1865e1d868d0bdd97897175c0.png)



下面是部分任务截图

![2019-10-11-18-10-22](https://blog-oeynet-com.oss-cn-chengdu.aliyuncs.com/b9a2dd21e26fb4f8c89d53deab8c3318.png)
![2019-10-11-14-25-42](https://blog-oeynet-com.oss-cn-chengdu.aliyuncs.com/d32bb6e91a8d1a2f1c4e23221dd5100e.png)

![2019-10-12-08-08-42](https://blog-oeynet-com.oss-cn-chengdu.aliyuncs.com/9e50972fc3b6778fcf11dfc2ece6e48a.png)
![2019-10-12-08-14-00](https://blog-oeynet-com.oss-cn-chengdu.aliyuncs.com/0ed28b24e443a6f035b07d625503c670.png)


## 架构

1.nodejs api端提供web服务

2.golang 消息队列消费任务

## 租用资源

联系我

## 计划

-   1.开放部分API
-   2.支付宝自动扫码付款插件（开放源代码）
-   3.订单后续实时同步查询状态

### 协议

授权协议：只允许研究、学习目的的分享、使用、修改，不允许任何商业用途。转载请注明出处，感谢。


