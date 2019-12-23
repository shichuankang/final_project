# 相册管家

| 发布日期 | 2019.12.8    |
| -------- | ------------ |
| 产品名称 | 相册管家 |
| 文档状态 | 进行中       |
| 文件主人 | 施传康       |
| 设计者   | 施传康       |
| 开发者   | 施传康       |

## 产品定位
> 本产品是一个智能手机相册app，运用通用图像识别与地理定位服务api，帮助用户给每张图片添加标签，给用户提供一个整洁有序的相册。
## 目标用户
> 喜欢用手机拍照记录生活的手机使用群体
## 市场背景
> 目前市场上的手机相册app都没有自动为照片添加标签的功能，只能用户自己给照片进行分组，不然相册都很乱，难以第一时间找到自己要的照片。
## 加值宣言
> 本app使用2个api实现app自动给图片添加标签的主要功能，分别是通用图像识别api和地理定位服务api。希望本app能帮助到用户，让其有存在的价值。
## 用户痛点
> 手机拍照非常方便，大家平常都喜欢随手拍下各种照片来记录生活，日积月累整个相册凌乱不堪，用户难以第一时间找到自己想要的照片。
## 核心价值
* 通用图像识别：通过通用图像识别识别图片内容，添加一个内容标签
* 地理定位服务：通过地理定位服务api，添加一个地理标签
## 用到的api
* 百度云通用图像识别api
* 阿里云定位服务api
## 用户画像
* 张小姐：大学刚毕业，旅游爱好者，喜欢用手机记录旅游点滴，日积月累手机图片超级多，想找图片时很难找到，使用了本app后解决了此烦恼。
* 王同学：大学生，平时喜欢用手机相机拍摄日常生活，日积月累手机图片很多，想找图片时很难找到，使用了本app后解决了此烦恼。
## 目标
* 前期目标：app自动为图片添加标签，用户搜索标签找到图片。
* 后期目标：app根据标签给图片进行分类。
## API使用与输出
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
f = open(r'C:\Users\我我我\Desktop\9.jpg', 'rb')  #上传想识别物体的照片
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
