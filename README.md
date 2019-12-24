# 相册管家

| 发布日期 | 2019.12.8    |
| -------- | ------------ |
| 产品名称 | 相册管家 |
| 文档状态 | 进行中       |
| 文件主人 | 施传康       |
| 设计者   | 施传康       |
| 开发者   | 施传康       |

## 价值主张设计
### 产品定位
> 本产品是一个智能手机相册app，使用通用物体和场景识别api识别图片主体内容，帮助用户给每张图片添加标签，给用户提供一个整洁有序的相册。用户还可以一键转换图片风格，让用户的图片变的更有趣。
### 目标用户
> 喜欢用手机拍照记录生活的手机使用群体
## 市场背景
> 目前市场上的手机相册app都没有自动为照片添加标签的功能，只能用户自己给照片进行分组，不然相册都很乱，难以第一时间找到自己要的照片。
### 加值宣言
> 本app使用通用物体和场景识别api实现app自动给图片添加标签的主要功能，使用百度云图像风格转换api让用户可以一键转换图片风格。希望本app能帮助到用户，让其有存在的价值。
### 用户痛点
> 手机拍照非常方便，大家平常都喜欢随手拍下各种照片来记录生活，日积月累整个相册凌乱不堪，用户难以第一时间找到自己想要的照片。
> 用户想要转换图片的风格只能下载专门的美图软件。
### 核心价值
* 通用物体和场景识别：通过通用图像识别识别图片内容，添加一个内容标签
* 图像风格转换：通过图像风格转换api一键转换图片风格
### 用到的api
* 百度云通用物体和场景识别api
* 百度云图像风格转换api
### 用户画像
* 张小姐：大学刚毕业，旅游爱好者，喜欢用手机记录旅游点滴，日积月累手机图片超级多，想找图片时很难找到，使用了本app后解决了此烦恼。
* 王同学：大学生，喜欢拍照，喜欢二次元，手机图片很多，难以第一时间找到，想转换图片风格只能打开p图软件，使用了本app后解决了找不到图片的烦恼，也能一键转换图片风格，不用再专门打开p图软件。
### 目标
* 前期目标：1.app自动为图片添加标签，用户搜索标签找到图片。2.一键转换图片风格。
* 后期目标：app根据标签给图片进行分类。

## 产品原型
### 交互及界面设计
#### 启动页与首页
![启动页.png](https://upload-images.jianshu.io/upload_images/9734328-38b245925931eb4d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![首页.png](https://upload-images.jianshu.io/upload_images/9734328-3153b52232b6e04b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

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
### API概率性

![测试1](https://upload-images.jianshu.io/upload_images/9734328-8ac37409bd07fd71.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
当图片主体在图片中占比较小时，会出现识别出错误结果的情况。

![测试2](https://upload-images.jianshu.io/upload_images/9734328-2616efc88b85f9f5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
当图片色调较暗时，主体不突出时，会出现识别出错误结果的情况。

![测试3](https://upload-images.jianshu.io/upload_images/9734328-a7b071d189611494.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

当图片主题较多时，会识别出较为突出的那个主体。
### 使用对比分析
* 腾讯云图像分析api
> 使用链接：https://cloud.tencent.com/product/tiia

![腾讯云图像分析api](https://upload-images.jianshu.io/upload_images/9734328-3ce08b55d59c7cce.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 阿里云图像识别api
> 使用链接：https://ai.aliyun.com/image?spm=5176.224200.100.129.378e6ed64FHJPe&aly_as=1V0J2MRH

![阿里云图像识别api](https://upload-images.jianshu.io/upload_images/9734328-35ce181506335927.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 百度云通用物体和场景识别api
> 使用链接：https://ai.baidu.com/tech/imagerecognition/general

![百度云通用物体和场景识别api](https://upload-images.jianshu.io/upload_images/9734328-014c1eb698f1ffb1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 对比分析
1. 通过3家图像识别api对同一张图片分析的结果可以看出，百度云通用物体和场景识别api识别出正确结果的概率大于其他2家api。
2. 价格方面，腾讯云与阿里云收费都为2.5元/千张，百度云的收费为2元/千张，低于其他2家。

* 总结
1. 虽然百度云通用物体和场景识别api在使用中也会出现识别出错的情况，但对比市场上其他相同类型的图像识别api，识别出正确结果的概率要大一些，而且价格方面也比其他的低，因此本app选择百度云通用物体和场景识别api作为主要功能使用的api。
2. 本app使用的另一个api为百度云图像风格转换api，查找了其他云平台，没有发现有类似的api，但此api不是分析类型的api，因此不会出现出错的情况。


