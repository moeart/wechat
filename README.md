# wechat

### 安装

环境要求：PHP >= 5.3.0

使用 `composer`

`composer require "stoneworld/wechat:~2.1" -vvv`

手动安装
下载 本安装包

然后引入根目录的autoload.php即可：

```
<?php

require "wechat/autoload.php"; // 路径请修改为你具体的实际路径

...
确认你没装 laravel-debugbar!!!!

```

### 使用

基本使用（以服务端为例）:

```
<?php

use Stoneworld\Wechat\Server;

$options = array(
            'token'=>'stoneworld1992',   //填写应用接口的Token
            'encodingaeskey'=>'o1wze3492xoUVIc9ccTLJczO3BQ5pLfiHcKwtDEdqM9',//填写加密用的EncodingAESKey
            'appid'=>'wx8ac123b21f53dera7',  //填写高级调用功能的appid
            'appsecret'=>'4ZDHIETJ6e0oENlEkRhYwdKcPcRjCkgQkuHtQTJ12ZhWHESowrJqS9', //填写高级调用功能的密钥
            'agentid'=>'5', //应用的id
        );

$server = new Server($options);

$server->on('message', function($message){
    return "您好!";
});

// 您可以直接echo 或者返回给框架
echo $server->server();
```

更多请参考文档[wiki](https://github.com/stoneworld/wechat/wiki/%E5%86%99%E5%9C%A8%E5%89%8D%E9%9D%A2)。

### 致谢

特别感谢超哥 [安正超 @overtrue](https://github.com/overtrue) 的 EasyWeChat 微信 SDK 为企业微信 SDK 开发带来的指引。

### License

MIT

