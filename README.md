# 数字货币量化交易-网格策略

### 介绍
这是一款能够快速上手的量化项目，采用网格交易策略

其中只使用到了交易所的3个api接口。
1. 获取某个交易对的当前价格
2. 限价挂单 Maker
3. 限价挂单 Taker

### 优势：🎉
1. 简单易上手
2. 安全(不用将api_secret告诉人)

### 为什么选择币安交易所
最开始我使用的是火币网的api接口来做量化交易，久而久之，我发现交易的手续费看起来很少，但是一个月下来也是一笔不小的数目。所以我得赶忙找一个手续费低的大平台交易所，所以我选择了币安
> 火币手续费 Maker 0.2% Taker 0.2%

> 币安手续费 Maker 0.1% Taker 0.1%

### 如何启动

1. 修改app目录下的authorization文件

```
api_key='你的key'
api_secret='你的secret'

dingding_token = '申请钉钉群助手的token'   # 建议您使用
```

如果你还没有币安账号：[注册页面](https://www.binance.com/cn/register?ref=50178251)

申请api_key地址: [币安API管理页面](https://www.binance.com/cn/usercenter/settings/api-management)

2. 修改data/data.json配置文件
```
{
    "runBet": {
        "next_buy_price": 350,      <- 下次开仓价
         
        "grid_sell_price": 375      <- 当前止盈价
    },
    "config": {
        "profit_ratio": 5,         <- 止盈比率
        "double_throw_ratio": 5,   <- 补仓比率
        "cointype": "ETHUSDT",     <- 交易对
        "quantity": 1              <- 交易数量
    }
}
```
3. 运行主文件
```
python eth-run.py

# python eth-run-msg.py 这是带有钉钉通知的主文件(推荐使用钉钉模式启动👍)
```

### 钉钉预警

如果您想使用钉钉通知，那么你需要创建一个钉钉群，然后加入自定义机器人。最后将机器人的token粘贴到authorization文件中的dingding_token
关键词输入：报警

#### 钉钉通知交易截图

![钉钉交易信息](https://s1.ax1x.com/2020/10/10/0ytKdH.md.jpg)
#### 近日收益
![收益图](https://s1.ax1x.com/2020/10/10/0ya4Yj.md.png)

### 待办事项
- [ ] 支持不同仓位倍投数量不同
- [ ] 交易结果汇总,计算总收益值
- [ ] 支持均值回归策略,三角套利

### 私人微信：欢迎志同道合的朋友一同探讨，一起进步
![wechat-QRcode](https://s3.ax1x.com/2020/11/14/DPSYss.jpg)
麻烦备注来自github
### 免责申明
本项目不构成投资建议，投资者应独立决策并自行承担风险

币圈有风险，入圈须谨慎。
### 注意事项
由于交易所的api在大陆无法访问
所以以上操作必须在**科学上网**的基础上才能运行

运行项目使用的是腾讯云的海外服务器

> 🚫风险提示：防范以“虚拟货币”“区块链”名义进行非法集资的风险。
