# Heroku-QyWechatPush

#### 源码修改自[MrZhang1899/WxWork_Push]，感谢开源

修改内容：将原先需要填入index.php的个人信息变为部署时填写环境变量

#### 部署方式

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/requireCool/Heroku-QyWechatPush)

## 以下教程来自原作者项目[MrZhang1899/WxWork_Push](https://github.com/MrZhang1899/WxWork_Push)

### WxWork_Push是什么

利用企业微信的Api，实现推送消息到微信上

是一款类似于server酱Turbo版的一款「程序员」和「服务器」之间的通信软件

注：不需要使用到企业微信，只需要获取 `cropid` `secret` `agentid`三个值即可，获取方式在[这里](https://github.com/requireCool/Heroku-QyWechatPush#%E5%8F%82%E6%95%B0%E8%8E%B7%E5%8F%96)

### WxWork_Push使用方式

#### 使用方式

在部署时的环境变量中填入 `cropid` `secret` `agentid`三个值，用GET参数请求

访问方式1（消息推送）：http://你的应用域名/?msg=消息内容

访问方式2（实时天气推送）：http://你的应用域名/?type=weather&loc=位置


#### 参数说明

| URL参数| 必须| 说明 |
| ------------ | ------------ | ------------ |
| /?msg= | 二选一 | 推送内容，最长不超过2048个字节，否则截断 |
| /?type=weather&loc= | 二选一 | 推送天气，loc后接地区参数 |

注：`loc` 默认 广州天河，可在 `weather.php` 中修改，参数可在 [https://www.tianqi.com/](https://www.tianqi.com/chinacity.html) 中查看


#### 返回实例
<pre>
{"errcode":0,"errmsg":"ok","invaliduser":""}
</pre>

注：`errcode` 代码请查看企业微信官方文档详细解析 >[点击查看](https://work.weixin.qq.com/api/doc/90000/90139/90313)


### 参数获取
如果没有创建企业，请自行注册企业，可以不用验证

**1. corpid 获取**

点击 [此处](https://work.weixin.qq.com/wework_admin/frame#profile) 登陆企业微信，点击我的企业，最下面就是企业ID

![企业ID.png](https://i.loli.net/2021/02/22/kmAyYGjxZe2C5pM.png)

**2. secret 和 agentid 获取**

点击应用管理，点击创建应用，自行填写资料，创建好后即可看到

![secret和agentid获取1](https://i.loli.net/2021/02/22/ZRutYNels41IFDU.png)
![secret和agentid获取2](https://i.loli.net/2021/02/22/arqSobE7kxNDwYX.png)
