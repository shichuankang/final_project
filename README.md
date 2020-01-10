# 印相--您的专属相册管家

| 发布日期 | 2019.12.8    |
| -------- | ------------ |
| 产品名称 | 印相         |
| 文档状态 | 完成         |
| 文件主人 | 施传康       |
| 设计者   | 施传康       |
| 开发者   | 施传康       |
[20*20PowerPoint观看](https://pan.baidu.com/s/1KovAehd5W_qdXW20mGBxxA)
[20*20PowerPoint下载](https://github.com/shichuankang/final_project/blob/master/api%E6%BC%94%E7%A4%BA.pptx)

# 目录
- [价值主张设计](#价值主张设计)
    - [加值宣言](#加值宣言)
    - [核心价值](#核心价值)
    - [核心价值与用户痛点](#核心价值与用户痛点)
    - [人工智能概率性与用户痛点](#人工智能概率性与用户痛点)
    - [需求列表与人工智能API加值](#需求列表与人工智能API加值)
- [产品原型](#产品原型)
    - [交互及界面设计](#交互及界面设计)
    - [信息设计](#信息设计)
    - [产品架构图](#产品架构图)
    - [原型文档](#原型文档)
    - [口头操作说明](#口头操作说明)
- [API使用与输出展示](#API使用与输出展示)
    - [API使用与输出](#API使用与输出)
    - [使用对比分析](#使用对比分析)
    - [使用后风险报告](#使用后风险报告)
    - [加分项](#加分项)

## 价值主张设计

### 加值宣言
手机拍照非常方便，大家平常都喜欢随手拍下各种照片来记录生活，日积月累整个相册凌乱不堪，用户难以第一时间找到自己想要的照片。本app使用通用物体和场景识别api实现app自动给图片添加标签的主要功能，使用百度云图像风格转换api实现让用户可以一键转换图片风格的辅助功能。帮助用户解决了问题的同时也让用户有了更好的体验。
#### 功能优先级
* 主要：通用物体和场景识别api：支持超过10万类常见物体和场景识别，接口返回图片内1个或多个物体的名称
* 次要：图像风格转换api：将图像转换成卡通画或素描风格，可用于开展趣味活动

### 核心价值
* 通用物体和场景识别：最小可用产品为通过通用图像识别识别图片内容，添加一个内容标签
* 图像风格转换：最小可用产品为转换图片风格

### 核心价值与用户痛点
 |  核心价值 | 用户痛点 |
 | -- | -- |
 |  **标签化** | 当手机图片较多时难以第一时间找到自己想要的图片。 |
 |  **转换风格** | 用户想要让自己的图片变得有趣时只能打开另外的美图软件。 |


### 人工智能概率性与用户痛点

![测试1](https://upload-images.jianshu.io/upload_images/9734328-8ac37409bd07fd71.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

当图片主体在图片中占比较小时，会出现识别出错误结果的情况。

![测试2](https://upload-images.jianshu.io/upload_images/9734328-2616efc88b85f9f5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

当图片色调较暗时，主体不突出时，会出现识别出错误结果的情况。

![测试3](https://upload-images.jianshu.io/upload_images/9734328-a7b071d189611494.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

当图片主体较多时，会识别出较为突出的那个主体。

* 当图片主体较小时，识别出错的概率较大。
* 当图片色调较暗时，识别出错的概率较大。
* 当图片主体较多时，识别的结果为较突出的主体。

### 需求列表与人工智能API加值
|  用户需求  | API接口  | 重要程度  |
|  ----  | ----  | ----  |
| 在相册中快速找到自己想找的图片  | 通用物体和场景识别api | 重要 |
| 一键给图片转换风格，让图片变有趣 | 图像风格转换api | 次重要 |


## 产品原型
### 交互及界面设计
#### app启动页与首页

![首页与启动页](https://upload-images.jianshu.io/upload_images/9734328-cab9ad1c0ae716be.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 拍照识别流程图

![拍照识别流程](https://upload-images.jianshu.io/upload_images/9734328-863e94e158018540.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




#### 查看相册

![查看相册流程](https://upload-images.jianshu.io/upload_images/9734328-76a8466fac440319.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 查找图片流程图

![查找图片流程](https://upload-images.jianshu.io/upload_images/9734328-e2f5033f6ce177a5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 图片转换风格流程图

![转换风格流程](https://upload-images.jianshu.io/upload_images/9734328-7cb6487fc2eb2338.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 信息设计

#### 图片识别api输出结果

![输出结果1](https://upload-images.jianshu.io/upload_images/9734328-a119a59bc694ff42.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 图像风格转换api输出结果

![输出结果2](https://upload-images.jianshu.io/upload_images/9734328-f223565f575d1386.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 产品架构图

![产品架构图.png](https://upload-images.jianshu.io/upload_images/9734328-df041c75c45b4a3b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 原型文档
* 原型链接：[印相app原型](http://nfunm072.gitee.io/api-app)
* 原型下载：[原型下载链接](https://gitee.com/NFUNM072/api-app)

### 口头操作说明
> 本产品是一个智能手机相册app，使用了2个人工智能api--通用物体和场景识别api、图像风格转换api。第一个功能为app通过通用物体和场景识别api识别图片主题内容给图片添加标签，操作流程为用户[拍摄照片](http://nfunm072.gitee.io/api-app/#g=1&p=拍照)后，等待app分析，得到[分析结果](http://nfunm072.gitee.io/api-app/#g=1&p=识别结果)后点击保存即可添加此有标签的图片。接下来用户就可以在[搜索图片页面](http://nfunm072.gitee.io/api-app/#g=1&p=查找图片)输入标签找到自己想要的图片。第二个功能为一键转换图片的风格，操作流程为用户[选择想要转换风格的图片](http://nfunm072.gitee.io/api-app/#g=1&p=转换风格)，然后在[选择风格页面](http://nfunm072.gitee.io/api-app/#g=1&p=选择风格)中选择想要转换的风格，即可得到转换风格后的图片。

## API使用与输出展示

### API使用与输出
1. 百度云通用物体和场景识别API
* 接口描述：该请求用于通用物体及场景识别，即对于输入的一张图片（可正常解码，且长宽比适宜），输出图片中的多个物体及场景标签。
* HTTP 方法：POST
* 请求URL： https://aip.baidubce.com/rest/2.0/image-classify/v2/advanced_general
* 输入代码
```
# encoding:utf-8

import requests
import base64

'''
通用物体和场景识别
'''

request_url = "https://aip.baidubce.com/rest/2.0/image-classify/v2/advanced_general"
# 二进制方式打开图片文件
f = open(r'C:\Users\我我我\Desktop\9.jpg', 'rb')
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '24.864ce070899da72bdcb9b2bd15defda5.2592000.1579690807.282335-18092023'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
* 输出结果
```
{'log_id': 7694512957233731095, 'result_num': 5, '
 result': [{'score': 0.190906, 'root': '植物-树', 'keyword': '树'}, 
 {'score': 0.142538, 'root': '交通工具-轮船', 'keyword': '木船'}, 
 {'score': 0.095388, 'root': '非自然图像-艺术画', 'keyword': '油画'}, 
 {'score': 0.048282, 'root': '建筑-室内', 'keyword': '室内一角'}, 
 {'score': 0.002822, 'root': '交通工具-轮船', 'keyword': '轮船'}]}
```
2. 百度云图像风格转换API
* 接口描述：将图像转化成卡通画或素描风格。
* HTTP 方法：POST
* 请求URL： https://aip.baidubce.com/rest/2.0/image-process/v1/style_trans
* 输入代码
```
# encoding:utf-8

import requests
import base64

'''
图像风格转换
'''

request_url = "https://aip.baidubce.com/rest/2.0/image-process/v1/style_trans"
# 二进制方式打开图片文件
f = open(r'C:\Users\我我我\Desktop\9.jpg', 'rb')
img = base64.b64encode(f.read())

params = {"image":img}
access_token = '24.a0cff753e5846c3d480085f3b77be208.2592000.1579705686.282335-18093245'
request_url = request_url + "?access_token=" + access_token
headers = {'content-type': 'application/x-www-form-urlencoded'}
response = requests.post(request_url, data=params, headers=headers)
if response:
    print (response.json())
```
* 输出示例

![示例图片](https://upload-images.jianshu.io/upload_images/9734328-f41819b23b0435f8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![转换结果](https://upload-images.jianshu.io/upload_images/9734328-4934cc515686e0f9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



### 使用对比分析
#### 腾讯云图像分析api
> 使用链接：https://cloud.tencent.com/product/tiia

![腾讯云图像分析api](https://upload-images.jianshu.io/upload_images/9734328-3ce08b55d59c7cce.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 阿里云图像识别api
> 使用链接：https://ai.aliyun.com/image?spm=5176.224200.100.129.378e6ed64FHJPe&aly_as=1V0J2MRH

![阿里云图像识别api](https://upload-images.jianshu.io/upload_images/9734328-35ce181506335927.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 百度云通用物体和场景识别api
> 使用链接：https://ai.baidu.com/tech/imagerecognition/general

![百度云通用物体和场景识别api](https://upload-images.jianshu.io/upload_images/9734328-014c1eb698f1ffb1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 对比分析
1. 通过3家图像识别api对同一张图片分析的结果可以看出，百度云通用物体和场景识别api识别出正确结果的概率大于其他2家api。
2. 价格方面，腾讯云与阿里云收费都为2.5元/千张，百度云的收费为2元/千张，低于其他2家。

#### 总结
1. 虽然百度云通用物体和场景识别api在使用中也会出现识别出错的情况，但对比市场上其他相同类型的图像识别api，识别出正确结果的概率要大一些，而且价格方面也比其他的低，因此本app选择百度云通用物体和场景识别api作为主要功能使用的api。
2. 本app使用的另一个api为百度云图像风格转换api，查找了其他云平台，没有发现有类似的api，但此api不是分析类型的api，因此不会出现出错的情况。

### 使用后风险报告
#### 百度云通用图像与场景识别api
* 准确性：通过对比百度云通用图像与场景识别api和其他2家相同类型图像识别api，发现百度云通用图像与场景识别api识别出正确结果的概率大于其他2家。
* 价格：价格方面百度云通用图像与场景识别api为2元/千张，而其他2家都为2.5元/千张。
* 总结而言，百度云通用图像与场景识别api不管在准确性还是在价格方面上对比其他2家都有优势，但百度云通用图像和场景识别api也会出现识别错误的情况。
#### 百度云图像风格转换api
* 市场上没有其他云平台有类似百度云图像风格转换的api，百度云图像风格api因为其类型不是分析类型，因此不会出现错误的情况。

### 加分项
* 百度云通用图像与场景识别api：[调用链接](https://ai.baidu.com/ai-doc/IMAGERECOGNITION/Xk3bcxe21)
* 百度云图像风格转换api：[调用链接](https://ai.baidu.com/ai-doc/IMAGEPROCESS/xk3bclo77)




