# BaiduAi
### 概述
最好用的百度AI  
BaiduAi 是一个开源的 百度 非官方 SDK。  
BaiduAi 的安装非常简单，因为它是一个标准的 Composer 包，这意味着任何满足下列安装条件的 PHP 项目支持 Composer 都可以使用它。
### 安装
###### 使用 composer:
`$ composer require liuming9157/baiduai`
### 文字识别入门
```
use BaiduAi\AipOcr;
// 你的 APPID AK SK
const APP_ID = '你的 App ID';
const API_KEY = '你的 Api Key';
const SECRET_KEY = '你的 Secret Key';

$client = new AipOcr(APP_ID, API_KEY, SECRET_KEY);

$image = file_get_contents('example.jpg');

// 调用通用文字识别, 图片参数为本地图片
$client->basicGeneral($image);

// 如果有可选参数
$options = array();
$options["language_type"] = "CHN_ENG";
$options["detect_direction"] = "true";
$options["detect_language"] = "true";
$options["probability"] = "true";

// 带参数调用通用文字识别, 图片参数为本地图片
$client->basicGeneral($image, $options);
$url = "http//www.x.com/sample.jpg";

// 调用通用文字识别, 图片参数为远程url图片
$client->basicGeneralUrl($url);

// 如果有可选参数
$options = array();
$options["language_type"] = "CHN_ENG";
$options["detect_direction"] = "true";
$options["detect_language"] = "true";
$options["probability"] = "true";

// 带参数调用通用文字识别, 图片参数为远程url图片
$client->basicGeneralUrl($url, $options);
```

