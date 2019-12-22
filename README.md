# 智能毕业纪念册

### Product Requirements
|Target release|2019-12-22|
|---|---|
|Epic|智能毕业纪念册|
|Document status|已完成|
|Document owner|黄煜惠|
|Designer|黄煜惠|
|Developer|黄煜惠|

# PRD 价值主张设计
## 背景
校园生活对于大多数人来说是美好的、值得纪念的，毕业生需要通过毕业纪念册来记录自己学业生涯中的美好回忆。目前，市面上已有很多专门制作相册的微信公众号、微信小程序和APP，但是这些产品的功能大多都千篇一律，没有创意。

## 目标
开发一个智能毕业纪念册，毕业生在查看照片时可立即得到照片上每个同学的个人信息；毕业生可以将照片储存在云端并分类；毕业生还可以在学校地图上的某个位置做标记，然后使用文字、照片或语音在该标记点记录重要事件。

## 加值宣言
智能云相册API在智能毕业纪念册中提供了影像文件存储、管理等基础功能，还支持对影像内容进行分类打标、面孔识别等智能分析，并提供基于自然语言理解的智能搜索服务，极大满足储存和管理的需求。

人脸搜索API将目标人脸与储存在人脸库中的人脸进行对比分析，返回两者相似度，若相似度高达98%以上，则调取人脸库中的个人信息，并将个人信息匹配到目标人脸上。

静态地图API可以让用户指定地图位置、图片大小以及在地图上做标记，从而达到在学校地图上记录重要事件的目的。

短语音识别API融合百度自然语言处理技术，实现语音输入和语音识别。

## 核心价值（最小可行性）
1. 通过人脸搜索，在一人或多人的照片中返回个人信息
2. 实现相册的云储存
3. 使用文字、照片或语音，在地图中作标记。

## 目标用户
（准）毕业生

## 用户画像
- 小蔡
- 22岁
- 大四准毕业生
- 在班上有关系好的同学，可是还有一部分同学不熟悉不认识
- 毕业纪念册需求：
    1. 和同学拍合照
    2. 毕业照不用占用手机相册的内存
    3. 希望浏览照片时可以得到同学们的个人信息
    4. 希望在将来某一天能通过照片记起在学校里的美好回忆

## 核心价值与用户痛点

**使用人脸搜索，使人脸与个人信息对应上。**
- 痛点一：毕业照整理人员通常需要将学生的脸和名字逐个对应，花费很长时间。

**使用云相册**
- 痛点二：毕业照太多难以储存但是又不舍得删除。

**结合地图位置，记录特别的事件**
- 痛点三：毕业生回想不起来自己在校园里发生过的开心或不开心的事情。

**使用人脸搜索，使人脸与个人信息对应上。**
- 痛点四：毕业生毕业后想找某位同学的联系方式却找不到。

## 人工智能概率性与用户痛点
人工智能的准确率并不是百分百的，所以API可能出现以下的问题：
- 人脸搜索API：因拍照角度、长相相似等问题，将毕业生识别错误，为毕业生带来额外的困扰
- 智能云相册API：照片分类错误，还需要自己手动调整分类
- 静态地图API：定位不准确，原有的在定位点记录事件的功能失去意义
- 短语音识别：近场中文普通话识别准确率达98%，但其他方言的准确率未达98%，为普通话不太标准的毕业生带来困扰

## 需求列表与人工智能API加值

### 用户需求
| |优先级|需求|API的使用|
|---|---|---|---|
|1|高|人脸识别与个人信息输出|百度-[人脸搜索API](https://ai.baidu.com/tech/face/search)|
|2|高|照片的云存储|阿里云-[智能云相册API](https://help.aliyun.com/document_detail/59902.html?spm=5176.10609282.905295.17.469838010yyDq4)|
|3|中|校园中特定地点的回忆记录|高德地图-[静态地图API](https://lbs.amap.com/api/webservice/guide/api/staticmaps)、百度-[短语音识别API](https://ai.baidu.com/tech/speech/asr)|
