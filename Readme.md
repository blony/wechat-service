# Node.js RESTful API for Wechat ![git start](https://img.shields.io/github/stars/blony/wechatservice.svg?style=social&label=Star) ![git fork](https://img.shields.io/github/forks/blony/wechatservice.svg?style=social&label=Fork) [![](https://img.shields.io/github/issues/blony/wechatservice.svg?style=social&label=Issues)](https://github.com/blony/wechatservice/issues) [![](https://img.shields.io/github/release/blony/wechatservice.svg?style=social&label=Releases)](https://github.com/blony/wechatservice/releases)

![node version](https://img.shields.io/badge/node-10.1.0-brightgreen.svg)
![npm version](https://img.shields.io/badge/npm-6.4.1-brightgreen.svg)
![express version](https://img.shields.io/badge/express-4.15.3-blue.svg)
![xml2js](https://img.shields.io/badge/xml2js-0.4.17-orange.svg)

# 项目结构
<pre>
.
├── wechat                      // 微信模块文件夹
│   ├── access_token.json       // accessToken存储文件
│   ├── cryptoGraphy.js         // 消息加/解密文件
│   ├── menus.json              // 菜单配置文件
│   ├── msg.js                  // 消息模块
│   └── wechat.js               // 基础模块          
├── app.js                      // 项目启动入口
├── config.json                 // 项目配置文件
├── package.json                // 构建项目与工具包依赖
├── README.md                   // 说明书
</pre>

# 目标功能
- [x] 微信接入功能
- [x] access_token的获取、存储及更新
- [x] 自定义微信菜单
- [ ] 模板消息
- [x] 消息被动回复
- [x] 消息加解密

# 构建项目
 1. 将项目 clone 到本地
    ```bash
    git clone git@github.com:blony/wechat-service.git
    ```

 2. 打开项目配置文件 config.json
 
    ```json
    {
    "token":"wechat",
    "appID":"wxa*******1c09",
    "appScrect":"ac62*********39fad58",
    "encodingAESKey":"q4YM7IW1***********NOtvrdYyHappIdCkPa",
    "apiDomain":"https://api.weixin.qq.com/",
    "apiURL":{
        "accessTokenApi":"%scgi-bin/token?grant_type=client_credential&appid=%s&secret=%s",
        "createMenu":"%scgi-bin/menu/create?access_token=%s"
             }
    }
    ```

    修改文件的 token、appID 以及 appScrect 配置参数。其中 token、appID 与 appScrect 两个参数位于 [微信公众平台](https://mp.weixin.qq.com/) 左侧菜单的基本配置中
    ![基本配置](http://img.blog.csdn.net/20170527134810969?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHZrQ29kZXI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

    ![开发着ID与秘钥](http://img.blog.csdn.net/20170601095037229?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHZrQ29kZXI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

 3. 进入 WeChatService 文件并运行 app.js
    ```bash
    cd WeChatService && node app.js  // Server runs at localhost:3000
    ```

 4. 将服务地址映射外网。
    

1. 接入认证

    ![接入认证](http://img.blog.csdn.net/20170527141026200?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHZrQ29kZXI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

    点击提交。提示提交成功，接入认证完成
    ![接入认证提交](http://img.blog.csdn.net/20170527141056778?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvaHZrQ29kZXI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
