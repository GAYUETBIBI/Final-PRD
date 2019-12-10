# APP:Keep Calling(保持通话)

## Product Requirement（产品说明文档）
|  Title   |  Content   |
| --- | --- |
|  Target release（发布日期）   |   2019-11-26  |
|   Epic（名称）  |   Keep Calling  |
|  Document status(文档状态)   |   进行中  |
|  Document owner(文件主人)   |  曾嘉悦   |
|   Designer(领头的设计师)  |  曾嘉悦   |
|   Developer(领头的开发者)  |  曾嘉悦   |    
|   QA(领头的测试者)  |  曾嘉悦   |


# PRD 价值主张设计

### PRD1.加值宣言 3%
本产品皆在通过使用阿里云人工智能的部分功能（语音识别、语音合成）使聋哑人以及听力衰退的老人也能像正常人用手机打电话，进行基本的社交活动。

* 语音合成API对本产品价值部分在于：高度拟人、流畅自然的语音合成，提供多场景音库；语速、音调可调节；支持多音字标注。
* 语音识别API对本产品价值部分在于：将语音快速准确识别为文字，支持手机应用语音交互、语音内容分析。


### PRD2.核心价值 3%
本产品主要面向聋哑人，听力受损的群体，调用语音识别、语音合成API，解决聋哑人难以打电话的问题，方便聋哑人进行基本的社交。


### PRD3.核心价值与用户痛点 3%
* 对于聋哑人来说唇语或者手语是唯一的交流方式
* 老年人人群中，超过65岁的老人们基本都会有听力下降的问题
* 遇到紧急情况的时候，电话就成了非常重要的联络的工具
* 聋哑人无法通过手机进行日常社交


### PRD4.人工智能概率性与用户痛点 3%
* 语音太模糊，导致识别的准确率低
* 可能存在部分聋哑人不识字的现象


### PRD5.需求列表与人工智能API加值 3%
#### 需求列表
|   标题  |  用户案例   |  重要程度   |
| --- | --- | --- |
|   实时语音转写  |  聋哑人通话   |   极其重要  |
|   语音文字识别  |  聋哑人通话   |   极其重要  |



### 原型1.交互及界面设计 5%
交互及界面设计：APP中的语音识别功能和语音合成功能，运用阿里云的智能语音识别API与语音合成API。

![通讯录界面](https://images.gitee.com/uploads/images/2019/1210/234009_7e3bfe60_1648179.png "qq.png")
![拨号页面](https://images.gitee.com/uploads/images/2019/1210/234226_09812169_1648179.png "dd.png")
![聊天界面](https://images.gitee.com/uploads/images/2019/1210/234253_849e413d_1648179.png "vv.png")

### 原型2.信息设计 5%
信息设计：
* APP打电话中说出对话将语音转为文字功能运用实时语音转写API，输出文本，实现语音转文字功能
* APP打电话中将文字转为语音功能运用实时语音转写API，输入音频，输出文本，实现音频转文字功能

### 原型3.原型文档 5%
原型文档：多少程度上有提供MVP可交互的原型文档，供它人在Github上下载使用

### 原型4.口头操作说明 5%
口头操作说明：聋哑人在生活中难以与正常人打电话沟通的现象十分普遍，保持通话APP可以帮助聋哑人与正常人打电话，进行基本的日常社交，更体现此APP在聋哑人遇到紧急情况时的作用。本APP运用阿里云的智能语音识别API与语音合成API，帮助聋哑人讲语音转化成文字，将语音转化为文本，使他们能与正常人打电话。


### API1.使用水平 5%
使用水平：输入
# -*- coding: utf8 -*-
import json
import time
from aliyunsdkcore.acs_exception.exceptions import ClientException
from aliyunsdkcore.acs_exception.exceptions import ServerException
from aliyunsdkcore.client import AcsClient
from aliyunsdkcore.request import CommonRequest
def fileTrans(akId, akSecret, appKey, fileLink) :
    # 地域ID，常量内容，请勿改变
    REGION_ID = "cn-shanghai"
    PRODUCT = "nls-filetrans"
    DOMAIN = "filetrans.cn-shanghai.aliyuncs.com"
    API_VERSION = "2018-08-17"
    POST_REQUEST_ACTION = "SubmitTask"
    GET_REQUEST_ACTION = "GetTaskResult"
    # 请求参数key
    KEY_APP_KEY = "appkey"
    KEY_FILE_LINK = "file_link"
    KEY_VERSION = "version"
    KEY_ENABLE_WORDS = "enable_words"
    # 是否开启智能分轨
    KEY_AUTO_SPLIT = "auto_split"
    # 响应参数key
    KEY_TASK = "Task"
    KEY_TASK_ID = "TaskId"
    KEY_STATUS_TEXT = "StatusText"
    KEY_RESULT = "Result"
    # 状态值
    STATUS_SUCCESS = "SUCCESS"
    STATUS_RUNNING = "RUNNING"
    STATUS_QUEUEING = "QUEUEING"
    # 创建AcsClient实例
    client = AcsClient(akId, akSecret, REGION_ID)
    # 提交录音文件识别请求
    postRequest = CommonRequest()
    postRequest.set_domain(DOMAIN)
    postRequest.set_version(API_VERSION)
    postRequest.set_product(PRODUCT)
    postRequest.set_action_name(POST_REQUEST_ACTION)
    postRequest.set_method('POST')
    # 新接入请使用4.0版本，已接入(默认2.0)如需维持现状，请注释掉该参数设置
    # 设置是否输出词信息，默认为false，开启时需要设置version为4.0
    task = {KEY_APP_KEY : appKey, KEY_FILE_LINK : fileLink, KEY_VERSION : "4.0", KEY_ENABLE_WORDS : False}
    # 开启智能分轨，如果开启智能分轨 task中设置KEY_AUTO_SPLIT : True
    # task = {KEY_APP_KEY : appKey, KEY_FILE_LINK : fileLink, KEY_VERSION : "4.0", KEY_ENABLE_WORDS : False, KEY_AUTO_SPLIT : True}
    task = json.dumps(task)
    print(task)
    postRequest.add_body_params(KEY_TASK, task)
    taskId = ""
    try :
        postResponse = client.do_action_with_exception(postRequest)
        postResponse = json.loads(postResponse)
        print (postResponse)
        statusText = postResponse[KEY_STATUS_TEXT]
        if statusText == STATUS_SUCCESS :
            print ("录音文件识别请求成功响应！")
            taskId = postResponse[KEY_TASK_ID]
        else :
            print ("录音文件识别请求失败！")
            return
    except ServerException as e:
        print (e)
    except ClientException as e:
        print (e)
    # 创建CommonRequest，设置任务ID
    getRequest = CommonRequest()
    getRequest.set_domain(DOMAIN)
    getRequest.set_version(API_VERSION)
    getRequest.set_product(PRODUCT)
    getRequest.set_action_name(GET_REQUEST_ACTION)
    getRequest.set_method('GET')
    getRequest.add_query_param(KEY_TASK_ID, taskId)
    # 提交录音文件识别结果查询请求
    # 以轮询的方式进行识别结果的查询，直到服务端返回的状态描述符为"SUCCESS"、"SUCCESS_WITH_NO_VALID_FRAGMENT"，
    # 或者为错误描述，则结束轮询。
    statusText = ""
    while True :
        try :
            getResponse = client.do_action_with_exception(getRequest)
            getResponse = json.loads(getResponse)
            print (getResponse)
            statusText = getResponse[KEY_STATUS_TEXT]
            if statusText == STATUS_RUNNING or statusText == STATUS_QUEUEING :
                # 继续轮询
                time.sleep(3)
            else :
                # 退出轮询
                break
        except ServerException as e:
            print (e)
        except ClientException as e:
            print (e)
    if statusText == STATUS_SUCCESS :
        print ("录音文件识别成功！")
    else :
        print ("录音文件识别失败！")
    return
accessKeyId = "您的AccessKey Id"
accessKeySecret = "您的AccessKey Secret"
appKey = "您的appkey"
fileLink = "https://aliyun-nls.oss-cn-hangzhou.aliyuncs.com/asr/fileASR/examples/nls-sample-16k.wav"

# 执行录音文件识别
fileTrans(accessKeyId, accessKeySecret, appKey, fileLink)

### API2.使用比较分析 5%
使用比较分析：在PRD文件中是否有说明且提供连结证据，所使用的API是查找过最适用的（主要竞争者无或比较次），如考量其成熟度丶性价比丶等等

### API3.使用后风险报告 5%
使用后风险报告：在PRD文件中是否有说明且提供连结证据，所使用的API类别的现在及未来发展性，如API市场竞争程度丶输入输出限制丶定价丶及可替代的程序库（改用自己开发的代码及数据库而不用API）等等

### API4.加分项 3%
使用复杂度：用了2个以上机器学习与人工智能的API之输入及输出
